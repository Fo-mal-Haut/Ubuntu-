# python安装

## 一、安装最新的python版本

```Shell
# 安装最新 Python 3（当前是 3.12）
brew install python

# 或安装特定版本
brew install python@3.11
brew install python@3.10
```

## 二、检查安装
```Shell
# 检查版本
python3 --version
python3 -V

# 检查安装路径
which python3
which pip3

# 查看详细信息
python3 --help
```

## 三、相关配置

### 1. 配置 VS Code

1. 安装 **Python 扩展**（Microsoft 出品）
2. 按 `Cmd+Shift+P`，输入 "Python: Select Interpreter"
3. 选择 `/opt/homebrew/bin/python3`（或你的虚拟环境）
4. 创建 `.vscode/settings.json`：
```json
{
    "python.defaultInterpreterPath": "/opt/homebrew/bin/python3",
    "python.linting.enabled": true,
    "python.formatting.provider": "black",
    "python.linting.flake8Enabled": true
}
```

### 2. 配置环境变量path

brew安装后，应该自动配置path，请检查：
```Bash
echo $PATH | grep homebrew

# 如果没有，手动添加
echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
source ~/.zshrc
```

## 四、实际情况说明

在安装验证的过程中，发现还是原来macOS自带的python3版本，即brew没有自动添加PATH。按照步骤三调整之后，才添加了brew安装的python14版本。
```shell
fomalhaut@192 game-theory % python3 -V
Python 3.9.6

fomalhaut@192 game-theory % which python3
/usr/bin/python3

fomalhaut@192 game-theory % which pip3
/usr/bin/pip3

fomalhaut@192 game-theory % echo $PATH | grep homebrew
/Users/fomalhaut/.nvm/versions/node/v24.13.0/bin:/opt/homebrew/bin:/opt/homebrew/sbin:/usr/local/bin:/System/Cryptexes/App/usr/bin:/usr/bin:/bin:/usr/sbin:/sbin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/local/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/bin:/var/run/com.apple.security.cryptexd/codex.system/bootstrap/usr/appleinternal/bin:/opt/pmk/env/global/bin

fomalhaut@192 game-theory % echo 'export PATH="/opt/homebrew/bin:$PATH"' >> ~/.zshrc
fomalhaut@192 game-theory % source ~/.zshrc

fomalhaut@192 game-theory % python3 -V
Python 3.14.3
```

