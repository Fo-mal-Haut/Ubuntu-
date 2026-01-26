# 安装路径

`dpkg`和`apt`在**最终的安装阶段和安装路径上是一致的**，因为它们**共用同一套底层的软件包管理系统和文件系统层次标准**。

## 安装路径相同

例如：firefox浏览器通过两种方式安装，安装路径都是 `/usr/bin/firefox`

这引出了另一个关键概念：**软件包格式规范**。

- `.deb` 包内部不仅包含程序文件，还包含一个**控制文件**，明确规定了**每个文件应该被安装到系统的哪个标准路径**（如可执行文件放 `/usr/bin`，库文件放 `/usr/lib`等）。

- 无论是APT从仓库下载的 `.deb` 包，还是从网上下载的 `.deb` 包，只要它们都是**为Ubuntu/Debian系统打包的**，就会遵循同样的规范。

- **因此，`dpkg` 在安装时，只是忠实地按照包内的指示，把文件复制到预定位置。** 所以同一个软件的不同版本（只要是合格的.deb包），安装路径自然相同。

## 完整的安装过程对比

以安装 `firefox` 为例，两种方式的实际流程如下：

**1. 通过 APT 安装**
```
你: sudo apt install firefox
↓
APT: 1. 查询仓库元数据，找到firefox包及其所有依赖包的下载链接。
     2. 从 archive.ubuntu.com 等镜像站下载所有必需的.deb包。
     3. 按照依赖顺序，逐个调用 dpkg -i 来安装这些.deb包。
     4. dpkg 将文件解压到指定位置（如 /usr/bin/firefox）。
结果: 一个完整可用的Firefox，包含所有依赖。
```

**2. 通过 dpkg 安装本地包**
```
你: 从Firefox官网下载 firefox-latest.deb
你: sudo dpkg -i firefox-latest.deb
↓
dpkg: 1. 直接解压 firefox-latest.deb。
      2. 将文件复制到预定位置（如 /usr/bin/firefox）。
结果: 同样得到一个安装位置相同的Firefox。
```

## Snap和Flatpak

不同于**传统的 `.deb` 包管理系统**，现代Ubuntu引入了**Snap和Flatpak**，它们是完全不同的打包格式和安装范式。

Snap和Flatpak将软件及其依赖封装在**独立的沙盒**中，安装路径完全不同（如Snap在 `/snap`，Flatpak在 `/var/lib/flatpak`）。

# 常用命令

**参考来源**：[dpkg-命令命令详解](https://www.cnblogs.com/xzongblogs/p/15535087.html)

`dpkg -i` 手动安装软件包(这个命令并不能解决软件包之前的依赖性问题),如果在安装某一个软件包的时候遇到了软件依赖的问题,可以用apt-get -f install在解决信赖性这个问题.  
　　　  
`dpkg --info "软件包名"` --列出软件包解包后的包名称.

`dpkg -l` --列出当前系统中所有的包.可以和参数less一起使用在分屏查看. (类似于rpm -qa)

`dpkg -l <package_name>` 查询软件包的信息  
　　　  
`dpkg -l |grep -i "软件包名"` --查看系统中与"软件包名"相关联的包.

`dpkg -s` 查询已安装的包的详细信息.

`dpkg -L` 查询系统中已安装的软件包所安装的位置. (类似于rpm -ql)

`dpkg -S` 查询系统中某个文件属于哪个软件包. (类似于rpm -qf)

`dpkg -I` 查询deb包的详细信息,在一个软件包下载到本地之后看看用不用安装

`dpkg -r` 卸载软件包.不是完全的卸载,它的配置文件还存在.

`dpkg -P` 全部卸载(但是还是不能解决软件包的依赖性的问题)

`dpkg -reconfigure` 重新配置
