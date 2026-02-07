可以参见[python安装实例](../Mac相关/brew/python安装实例.md)，有一定的记录。以下记录会涉及相关的安装配置问题

# 安装过程遇到的问题说明

## 一、`python -v`

- **`-V` (大写)**：是 `--version` 的缩写，用于显示版本号后**立即退出**。
- **`-v` (小写)**：是 `--verbose` 的缩写，它会**以详细模式启动 Python 解释器**，打印出所有模块导入的调试信息，然后进入交互式环境。

到进入到**Python解释器**中之后，通过**Ctrl + D**（macOS/Linux 通用）退出

## 二、pip与pip3

```Bash
fomalhaut@192 game-theory % which pip3 /opt/homebrew/bin/pip3 fomalhaut@192 game-theory % pip install -r requirements.txt zsh: command not found: pip
```

Homebrew 为了与 macOS 系统自带的 Python 2 的 `pip` 命令区分开，同时也遵循现代 Python 社区的惯例，**默认只创建 `pip3` 命令**，而不创建 `pip` 命令。

因而，需要直接用pip3命令：
```Shell
# 将命令中的 pip 替换为 pip3
pip3 install -r requirements.txt
```

## 三、环境管理问题

```SHell
fomalhaut@192 game-theory % pip3 install -r requirements.txt 

error: externally-managed-environment 
× This environment is externally managed
```

Homebrew 安装的 Python（`/opt/homebrew/bin/python3`）被标记为 **“外部管理环境”**。这是为了：

- **防止污染**：避免通过 `pip` 安装的包与 Homebrew 自己管理的包产生冲突。
- **确保可维护**：让 Homebrew 能干净地更新或卸载 Python，而不会被用户手动安装的包干扰。

**解决方法**：采用虚拟环境. （采用uv？[保姆级喂饭教程】uv教程一文讲透：安装，创建，配置，工具，命令](https://zhuanlan.zhihu.com/p/1938636637249700959))