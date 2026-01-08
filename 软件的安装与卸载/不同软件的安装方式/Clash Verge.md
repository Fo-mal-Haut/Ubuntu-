## 安装方式

在官方文档中，根据实际情况下载相应版本：Clash Verge Rev 下载页面：[点击查看](https://github.com/clash-verge-rev/clash-verge-rev)

下载完`.deb`文件后，移动到要安装的路径，在终端输入dpkg命令：

```Shell
sudo dpkg -i Clash.Verge.deb
```

## 出现问题

```text
dpkg: 依赖关系问题使得 clash-verge 的配置工作不能继续：
 clash-verge 依赖于 libwebkit2gtk-4.1-0；然而：
  未安装软件包 libwebkit2gtk-4.1-0。
```

处理依赖问题，可以直接通过apt解决：

```Bash
sudo apt install -f
```
