**参考文档**：[Jekyll官方文档](https://jekyll.ruby-lang.org.cn/docs/troubleshooting/#installation-problems "Permalink")
```
ERROR: While executing gem ... (Gem::FilePermissionError)
You don't have write permissions for the /Library/Ruby/Gems/2.6.0 directory
```
在执行 _gem_ 命令时遇到 _Gem::FilePermissionError_ 错误，核心原因是没有权限向系统 Ruby 的全局 gem 目录（如 `/var/lib/gems/`）写入文件

### 配置用户级 Gem 目录

这个方法的核心是设置两个环境变量：`GEM_HOME` 和 `PATH`。这不仅解决了权限问题，也避免了使用 `sudo` 可能带来的系统管理混乱和安全风险[](https://jekyll.ruby-lang.org.cn/docs/troubleshooting/#jekyll--macos)。

**操作步骤如下：**

1. **编辑 Shell 配置文件**  [bashrc文件](../../../Ubuntu/Linux基本知识/配置文件/bashrc文件.md)
打开 `~/.bashrc` 文件，在文件末尾添加以下三行：
```bash
# 配置用户gem安装目录
    export GEM_HOME="$HOME/.gem"
    export PATH="$HOME/.gem/bin:$PATH"
```
这行代码会配置用户 gem 安装目录并添加路径。

2. **使配置立即生效**  
    保存文件后，执行以下命令让配置在当前终端生效：
```bash
source ~/.bashrc
```
此操作可激活新导出的变量。

3. **验证配置并安装 Jekyll**  
重新打开一个终端，或运行以下命令检查环境变量是否已设置：
```bash
echo $GEM_HOME
# 应输出类似 /home/你的用户名/.gem
echo $PATH | grep gem
# 应能看到包含 .gem/bin 的路径
```

确认无误后，即可在不使用 `sudo` 的情况下安装 Jekyll 和 Bundler：
```bash
gem install jekyll bundler
```
此操作可在非 sudo 状态下安装 Jekyll。