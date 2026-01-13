# 安装方式

在官方文档中，根据实际情况下载相应版本：Clash Verge Rev 下载页面：[点击查看](https://github.com/clash-verge-rev/clash-verge-rev)

下载完`.deb`文件后，移动到要安装的路径，在终端输入dpkg命令：

```Shell
sudo dpkg -i Clash.Verge.deb
```

## dpkg方式安装路径

在终端运行：
```Bash
dpkg -L clash-verge
```
即可返回安装包的路径

# 安装问题

## 问题1：

**问题描述**：使用 `dpkg -i` 安装 `.deb` 包时遇到依赖错误，`clash-verge` 需要 `libwebkit2gtk-4.1-0` 这个库，但系统里没有。
返回的结果为：
```text
dpkg: 依赖关系问题使得 clash-verge 的配置工作不能继续：
 clash-verge 依赖于 libwebkit2gtk-4.1-0；然而：
  未安装软件包 libwebkit2gtk-4.1-0。
```

**核心原因**：系统中安装的C语言标准库（glibc）版本过旧，而`clash-verge`软件是依赖新版本库编译的。

处理依赖问题，可以直接通过apt解决,apt工具可以自动安装缺失的依赖包：
```Bash
sudo apt install -f
```
## 问题2：无法启动

点击软件图标后无法启动软件，需要通过终端运行查看问题，在终端运行：
```Bash
clash-verge
```
返回得到的报错如下：
```text
clash-verge: /lib/x86_64-linux-gnu/libc.so.6: version `GLIBC_2.38' not found (required by clash-verge)
clash-verge: /lib/x86_64-linux-gnu/libc.so.6: version `GLIBC_2.39' not found (required by clash-verge)
```
**核心原因**：系统中安装的C语言标准库（**glibc**）版本过旧，而`clash-verge`软件是依赖**新版本**库编译的。

