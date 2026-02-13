# MacOS系统

**1.查看ruby占用空间**
```Bash
# 1. 查看所有已安装的 Ruby 版本及其占用空间
du -sh ~/.rbenv/versions/*

# 示例输出：
# 102M    /Users/fomalhaut/.rbenv/versions/3.2.10
# 98M     /Users/fomalhaut/.rbenv/versions/3.1.4

# 2. 查看当前使用的 Ruby 版本占用空间
rbenv versions
du -sh ~/.rbenv/versions/$(rbenv version-name)

# 3. 查看 rbenv 全部占用（包括shims、缓存等）
du -sh ~/.rbenv
# 通常 200-500MB 左右
```

**2.查看Gem包的占用**
```Bash
# 查看当前 Ruby 版本的 gem 安装目录大小
du -sh $(gem environment gemdir)
du -sh $(gem environment gemdir)/gems/* | sort -hr | head -20  # 最大的20个gem

# 查看所有已安装 gem 的总数
gem list | wc -l

# 查看特定 gem 的占用
du -sh $(gem environment gemdir)/gems/rails-*
```

**3.查看 bundle 安装的项目依赖**

```Bash
# 在你的 Jekyll 项目目录中
cd ~/Developer/your-blog

# 查看项目依赖的 gem 占用
du -sh vendor/bundle 2>/dev/null || echo "没有 vendor/bundle"
du -sh ~/.rbenv/versions/*/lib/ruby/gems/*/gems/jekyll-* 2>/dev/null
```
