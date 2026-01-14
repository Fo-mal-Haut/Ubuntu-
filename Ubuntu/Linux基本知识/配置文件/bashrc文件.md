**参考资料**：
[【Linux】.bashrc 文件详解](https://blog.csdn.net/lph159/article/details/146260650)
[什么是 .bashrc，为什么要编辑 .bashrc？ | Linux 中国](https://zhuanlan.zhihu.com/p/33546077)
## 1. bashrc 的全称

.bashrc 是 Bash Shell 运行时读取的一个初始化文件，其全称是 Bourne Again Shell Run Commands。它在用户启动交互式非登录 Shell（如打开终端）时自动执行，用于配置环境变量、别名、提示符等。

## 2.为什么有bashrc

虽然存在很多不同的 shell，bash 却是最常见或许也是最主流的。如果你不明白那意味着什么，bash 是一个能解释你输入进终端程序的东西，并且基于你的输入来运行命令。它在一定程度上支持使用脚本来定制功能，这时候就要用到 `.bashrc` 了。

为了加载你的配置，bash 在每次启动时都会加载 `.bashrc` 文件的内容。每个用户的 home 目录都有这个 shell 脚本。它用来存储并加载你的终端配置和环境变量。

终端配置可以包含很多不同的东西。最常见的，`.bashrc` 文件包含用户想要用的别名。别名允许用户通过更短的名字或替代的名字来指向命令，对于经常在终端下工作的人来说这可是一个省时利器。

## 3. bashrc 的作用

- 设置环境变量（如 PATH）
- 定义 Shell 别名（alias）
- 配置 Shell 提示符（PS1）
- 自定义 Shell 行为（如自动补全）
- 运行用户自定义的 Shell 脚本
