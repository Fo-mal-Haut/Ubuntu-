# 修改环境变量

**参考资料**：[MacOS系统 配置环境变量的详细步骤](https://blog.csdn.net/weixin_43891869/article/details/148244852)

**步骤 1：确定 Shell 类型**

查看当前 Shell
输入以下命令确认使用的是 zsh 还是 bash：

```bash
echo $SHELL
```

如果输出` /bin/zsh`，编辑 `~/.zshrc`（macOS Catalina 及之后默认）。

如果输出 `/bin/bash`，编辑 `~/.bash_profile`。

**步骤 2：编辑环境变量文件**

方法一：使用 nano（适合新手）

打开配置文件
根据 Shell 类型选择命令：

```bash
nano ~/.zshrc        # Zsh 用户

# 或
nano ~/.bash_profile # Bash 用户
```

使用鼠标或触控板将光标移动到文件末尾，直接粘贴内容（例如添加 export PATH=$PATH:/your/custom/path）。
