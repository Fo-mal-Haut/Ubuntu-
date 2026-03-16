目前了解到MacBook上进行安装软件有四个方式：
1. **App Store**上进行安装下载，但是很多软件都无法在上面下载
2. “推拽安装”
	1. **.dmg 磁盘映像**，双击挂载为虚拟磁盘，手动将.app文件推拽到"application"中
	2. **.zip 压缩包**，解压后得到`.app`文件
3. **包管理器安装**，在MacOS中有一个类似于apt的[brew home](brew/brew%20home.md)。以vscode为例，安装命令为：
```Shell
brew install --cask visual-studio-code
```

# 安装位置查询

使用`brewhome`安装之后，可以通过命令去查询安装位置，例如：

```shell
# 查看 FreeSWITCH 安装的所有文件
brew list freeswitch

# 查看更详细的信息
brew info freeswitch
```

