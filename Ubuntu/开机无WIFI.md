有时候开机启动ubuntu,会出现没有WIFI连接可选的情况。这种情况常见于刚关机windows系统后再启动ubuntu系统，一般来说重启ubuntu系统即可连接wife。

但是反复的开启重启总不是很方便，因此需要找到问题的解决方法才行。在本笔记中记录几个连接wifi的方法，方便下次遇到这种情况可以离线调试。

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