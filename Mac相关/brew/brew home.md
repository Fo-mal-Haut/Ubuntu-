**参考资料**：
[当程序员拿到一台新Mac，构建全栈制霸环境](https://zhuanlan.zhihu.com/p/1993798551965291128),
[MacBook使用笔记：安装Homebrew（M1）](https://zhuanlan.zhihu.com/p/372576355)

之前浏览知乎文章时候，很多文章推荐Mac重要工具中，第一个永远是包管理工具**brewhome**，这个工具和apt类似，因而找了攻略进行下载。

# 官方源下载

在终端命令行窗口输入安装命令。

这里需要特别说明几点内容。

下面是Homebrew官方给出的安装命令：（如果没有VPN，不要使用此命令安装！）

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

通常情况下，官网给出的指令会报错：

```shell
curl: (7) Failed to connect to raw.githubusercontent.com port 443: Connection refused
```

因为这是国外网站，由于GFW（中国长城防火墙）的存在，如果没有vpn，是无法访问的，所以连接被拒绝！

# 国内源下载

以下为国内安装Homebrew的正确姿势：(基于gitee上某大神的自动安装脚本)

```shell
/bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"
```

回车执行指令后，根据提示操作。具体包括以下提示操作：

**（1）选择下载镜像**

根据需要选择下载源，例如，我这里选择中科大下载源，就输入‘1’，回车。

![](https://pic2.zhimg.com/v2-739f08cdbb3fb14802bfa91588278241_1440w.jpg)

**（2）确认删除旧版本**

如果存在旧版本，会弹出删除旧版本提示，输入"Y"，回车。

![](https://pic2.zhimg.com/v2-cf55167d8fe7a2a2ea3a43855e8f01cf_1440w.jpg)

**（3）输入开机密码（用于mac确认第三方应用安装）**

**（4）安装git**

如果之前没有安装过git，会终止homebrew安装，弹出git安装提示，点击“安装”。

![](https://picx.zhimg.com/v2-f9c32e6b0fbfded843d3fafa7b3448f7_1440w.jpg)

**（5）再次执行homebrew安装指令**

耐心等待git安装完成后，再次运行homebrew安装指令，重新根据提示操作即可。

安装需要一段时间，过程中，可以在终端看到脚本执行了那些操作。

![](https://pic4.zhimg.com/v2-bf1f0461a373e541af8be956dce862bf_1440w.jpg)

**（6）验证是否安装成功**

安装脚本执行完成后，重启终端。（重启后才生效）

通过在终端输入"brew -v"，可以查看homebrew版本。

如果正确输出版本信息，表示成功安装。

> 虽然叫做'Homebrew'，但实际使用时，命令是'brew'。

```shell
qiuxiannv@qiuxiannvdeMBP ~ % brew -v
Homebrew 3.1.7-42-gd45832b
Homebrew/homebrew-core (git revision 09d1a8b385; last commit 2021-05-15)
Homebrew/homebrew-cask (git revision c1dad4a5cf; last commit 2021-05-15)
```

> 在M1芯片上，homebrew的安装路径为：`"/opt/Homebrew/"`

# 运行过程记录

![](assets/brew%20home/20260207152929909.png)