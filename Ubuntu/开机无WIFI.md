有时候开机启动ubuntu,会出现没有WIFI连接可选的情况。这种情况常见于刚关机windows系统后再启动ubuntu系统，一般来说重启ubuntu系统即可连接wife。

但是反复的开启重启总不是很方便，因此需要找到问题的解决方法才行。在本笔记中记录几个连接wifi的方法，方便下次遇到这种情况可以离线调试。

# deepseek提供的方法

这是一个相当常见的双系统网络问题，根本原因是 **Windows 的“快速启动”功能**和 **无线网卡固件/驱动状态冲突**。

### 核心原因详解

1.  **Windows 的“快速启动”（Fast Startup）**：
    *   这个功能（默认开启）让 Windows 关机时并非完全关闭，而是将系统状态（包括驱动程序、内核会话）保存到一个休眠文件（`hiberfil.sys`）中。
    *   下次开机时，Windows 从这个文件快速恢复，而不是从头冷启动。
    *   **关键点**：在此过程中，**硬件（如无线网卡）的固件状态和内部寄存器也被 Windows 驱动设置并保持在了某种特定状态**。这种状态是为 Windows 优化或锁定的。

2.  **硬件的状态残留**：
    *   当你从这种“快速启动”的 Windows 重启到 Ubuntu 时，电脑执行的是“暖启动”，硬件（网卡）并没有经历完全的断电重启。
    *   网卡仍处于由 Windows 驱动设置和管理的特殊状态。Ubuntu 启动后，加载自己的开源驱动（如 `iwlwifi` 用于 Intel 网卡，`ath9k`, `mt76` 等用于其他网卡），但发现硬件处于一个它无法识别的或“锁定”的状态，导致驱动初始化失败。
    *   **表现就是：Ubuntu 完全检测不到无线网卡，`lspci` 或 `lsusb` 可能能看到硬件，但网络管理器中没有任何无线选项。**

3.  **完全重启的作用**：
    *   当你“关机”后再开机（尤其是在 Ubuntu 下选择“关机”，或者长按电源键强制断电），电脑经历了完整的断电过程。
    *   网卡和其他硬件被彻底重置，恢复到上电初始状态。
    *   此时启动 Ubuntu，驱动可以正常识别并初始化网卡，一切恢复正常。

### 解决方案（按推荐顺序）

#### 方案一：在 Windows 中彻底禁用“快速启动”（最推荐，一劳永逸）

这是根本的解决方法，能避免很多双系统间的硬件状态冲突。

1.  启动进入 **Windows**。
2.  打开 **控制面板** -> **硬件和声音** -> **电源选项**。
3.  点击左侧的 **“选择电源按钮的功能”**。
4.  点击 **“更改当前不可用的设置”**。
5.  在下方 **“关机设置”** 中，**取消勾选** **“启用快速启动（推荐）”**。
6.  点击 **“保存修改”**。
7.  重启电脑测试。

**注意**：这会让 Windows 开机慢几秒，但能彻底解决此问题以及可能存在的其他硬件兼容性问题。

#### 方案二：在从 Windows 切换到 Ubuntu 时，使用“重启”而非“关机再开机”

*   **原理**：在 Windows 中点击“重启”，Windows 会执行一个相对更彻底的关闭过程（不完全等同于完全断电，但比“快速启动”关闭更干净），有时可以重置硬件状态。
*   **方法**：在 Windows 里，点击“开始” -> 电源按钮 -> **“重启”**。然后在 BIOS/UEFI 启动菜单中选择 Ubuntu。
*   **效果**：这个方法有时有效，但不如方案一可靠，取决于具体硬件和驱动。

#### 方案三：在 Ubuntu 中手动重置无线网卡（命令行方法）

如果问题已经发生（进入Ubuntu后没WIFI），可以尝试以下命令来强制重置无线硬件。**注意：命令因网卡型号而异，可能需要尝试。**

1.  **查看网卡信息**：
    ```bash
    lspci | grep -i network
    ```
    或
    ```bash
    lsusb | grep -i wireless
    ```
    找到你的无线网卡型号（如 Intel AX200, Realtek RTL8822CE等）。

2.  **尝试常见重置方法**：
    *   **方法A：卸载并重新加载驱动模块**
        ```bash
        sudo modprobe -r <驱动模块名>   # 例如 iwlwifi, ath9k, mt76 等
        sudo modprobe <驱动模块名>
        ```
        **注意**：`<驱动模块名>` 需要根据你的网卡型号查找。执行 `lspci -k` 查看当前使用的内核驱动。
    *   **方法B：通过 rfkill 解锁**
        ```bash
        sudo rfkill unblock all
        ```
        （这个命令主要用于解除软件屏蔽，对你描述的问题可能无效，但值得一试）
    *   **方法C：使用 `airplane-mode` 脚本**（如果有安装）
        有些笔记本有飞行模式快捷键，尝试在 Ubuntu 里按一下飞行模式开关，再打开。

3.  **如果上述命令无效，最直接的方法仍然是：保存工作，然后执行一次完全关机再开机。**

### 总结

| 场景 | 现象 | 根本原因 | 最佳解决 |
| :--- | :--- | :--- | :--- |
| **先开 Ubuntu** | 网络正常 | 硬件从上电初始状态被 Linux 驱动正常初始化 | - |
| **先开 Windows（快速启动）-> 重启 -> Ubuntu** | 无 WIFI 选项 | Windows 驱动将网卡置于非常规状态，Linux 驱动无法接管 | **禁用 Windows 快速启动** |
| **完全断电后再开 Ubuntu** | 网络正常 | 硬件被完全重置 | - |

**强烈建议你采用方案一**，因为它是最干净、最彻底的解决方案，可以避免未来很多潜在的硬件冲突问题，且对系统性能几乎没有负面影响（只是 Windows 启动慢几秒）。

# 博客分享的解决方法
**参考来源**：[双系统Ubuntu开机wifi图标消失问题](https://www.naipings.cn/article/ubuntu/Module_Installation01)

### 最终成功的尝试

(1)我们须知：Ubuntu系统不显示wifi，通常都是Secure Boot没有关闭。对于win10/win11的电脑，BIOS设置中都有一个secure boot选项，默认情况下，win10/win11系统中的secure boot服务都是处于开启状态的，且无法进行关闭。

想要关闭secure boot服务，就必须进入BIOS程序界面。

对于联想笔记本电脑，其关闭Secure Boot的操作如下：

1. 开机一直按F2或（FN+F2）进入BIOS，按→方向键切换到Security，选择Secure Boot回车设置成Disabled,以关闭Secure Boot(安全启动)；

2. 转到Exit，把OS Optimized Defaults设置为Disabled或Other OS，，然后按F10保存即可。

# 腾讯云用户分享的解决方法
**参考来源**：[【已解决】Ubuntu无网络连接/无网络标识解决方法](https://cloud.tencent.com/developer/article/2425732)

## 可能的报错原因

原因一：硬件问题 Ubuntu无网络连接的一个常见原因是硬件故障，例如网线损坏、网卡故障或路由器问题。

原因二：驱动问题 另一个可能的原因是网络适配器的驱动程序不兼容或未正确安装。

原因三：系统设置问题 Ubuntu系统设置不当，如网络配置文件错误或网络服务未启动，也可能导致无网络连接。

原因四：网络服务问题

网络服务如NetworkManager未运行或配置错误，也可能导致网络连接问题。

## 排查原因

### 示例代码1：检查物理连接

检查物理连接是否正常，可以通过简单的命令行操作来测试网络连接：
```javascript
ping -c 4 google.com
```
这个命令会尝试向google.com发送4个ICMP回显请求，如果收到响应，则说明物理连接正常。

### 示例代码2：检查驱动程序

检查网络适配器驱动程序是否正确安装：
```javascript
lspci -vnn | grep -iA2 net
```
这个命令会列出所有网络接口及其详细信息，包括驱动程序状态。

### 示例代码3：检查网络配置文件

检查/etc/network/interfaces文件，确保网络配置正确：
```javascript
cat /etc/network/interfaces
```
这个命令会显示网络配置文件的内容，你可以检查是否有正确的配置，如：
```javascript
auto eth0
iface eth0 inet dhcp
```
这表示自动配置eth0接口，使用DHCP获取IP地址。

### 示例代码4：诊断网络服务

使用nmcli[命令行工具](https://cloud.tencent.com/product/cli?from_column=20065&from=20065)来诊断网络服务：
```javascript
nmcli d
```
这个命令会显示所有网络设备的状态，包括是否连接。

## 三、解决方案汇总

### 方案一：重启网络

启动网络服务并输入密码

```javascript
sudo systemctl start NetworkManager
```

重启网络服务
```javascript
sudo systemctl restart NetworkManager
```
### 方案二：解决Ubuntu的NetworkManager问题

更新NetworkManager的配置，得先有gedit或者vim，两个随意一个，这里用的gedit，没有就先弄gedit，有的话直接下一步。
```javascript
apt-get install gedit
```

用gedit打开NetworkManager.conf
```javascript
gedit /etc/NetworkManager/NetworkManager.conf
```
将第五行 managed=False 改为 managed=True ，然后 ctrl+s 保存后退出。

删除NetworkManager配置
```javascript
service NetworkManager stop
rm /var/lib/NetworkManager/NetworkManager.state 
service NetworkManager start 
```
然后重启即可恢复网络标识。

### 方案三：VM虚拟机管理设置

将vm中网络适配器从NAT模式换为桥接模式，或者桥接模式换为NAT模式。

# 终端结果

(base) **fomalhaut@fomalhaut-R2-D2**:**~**$ ping -c 4 google.com
ping: google.com: 域名解析出现暂时性错误
(base) **fomalhaut@fomalhaut-R2-D2**:**~**$ lspci -vnn | grep -iA2 net
0000:00:14.3 **Net**work controller [0280]: Intel Corporation Raptor Lake-S PCH CNVi WiFi [8086:7a70] (rev 11)
	Subsystem: Rivet **Net**works Device [1a56:1652]
	Flags: fast devsel, IRQ 18, IOMMU group 8
	Memory at 6205224000 (64-bit, non-prefetchable) [size=16K]
--
0000:6d:00.0 Ether**net** controller [0200]: Realtek Semiconductor Co., Ltd. Killer E2600 GbE Controller [10ec:2600] (rev 21)
	Subsystem: Acer Incorporated [ALI] Device [1025:170f]
	Flags: bus master, fast devsel, latency 0, IRQ 18, IOMMU group 25
(base) **fomalhaut@fomalhaut-R2-D2**:**~**$ cat /etc/network/interfaces
cat: /etc/network/interfaces: 没有那个文件或目录
(base) **fomalhaut@fomalhaut-R2-D2**:**~**$ nmcli d
DEVICE    TYPE      STATE         CONNECTION 
lo        loopback  连接（外部）  lo         
docker0   bridge    连接（外部）  docker0    
enp109s0  ethernet  不可用        --         
(base) **fomalhaut@fomalhaut-R2-D2**:**~**$ sudo systemctl start NetworkManager
[sudo] fomalhaut 的密码： 
(base) **fomalhaut@fomalhaut-R2-D2**:**~**$ sudo systemctl restart NetworkManager
(base) **fomalhaut@fomalhaut-R2-D2**:**~**$