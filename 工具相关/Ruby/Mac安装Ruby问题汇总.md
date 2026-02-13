# 网络问题

有时候Ruby或者Gem安装太慢，需要更换为国内源进行安装
```Bash
# 使用 Ruby China 镜像安装特定版本
export RUBY_BUILD_MIRROR_URL=https://cache.ruby-china.com
rbenv install 3.2.10

# 设置 gem 源为国内镜像（大幅加速）
gem sources --add https://gems.ruby-china.com/ --remove https://rubygems.org/
```

# 配置问题

## 问题描述
```Bash
fomalhaut@192 ~ % ruby -v
ruby 2.6.10p210 (2022-04-12 revision 67958) [universal.arm64e-darwin25]

fomalhaut@192 ~ % which ruby
/usr/bin/ruby
```

ruby的版本和路径都是macOS默认的路径

## 问题解决

**1.修改配置文件**
```Bash
# 打开配置文件
nano ~/.zshrc
```

修改配置文件如下：
```Bash
# 1. 将 rbenv 的 bin 目录加入 PATH（必须放在 PATH 设置的最前面）
export PATH="$HOME/.rbenv/bin:$PATH"

# 2. 初始化 rbenv（必须在 PATH 设置之后）
eval "$(rbenv init - zsh)"

# 3. Homebrew 的 PATH 应该放在 rbenv 之后
export PATH="/opt/homebrew/bin:$PATH"
```

**2.重新加载配置**
```Bash
# 1. 重新加载配置
source ~/.zshrc

# 2. 重新设置 Ruby 版本
rbenv global 3.2.10
rbenv rehash

# 3. 验证
ruby -v
which ruby
```
