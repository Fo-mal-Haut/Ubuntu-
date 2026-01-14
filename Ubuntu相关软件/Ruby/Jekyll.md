**参考信息**：[Jekyll官方文档](https://jekyllcn.com/docs/home/)
# 基本介绍

Jekyll 是一个简单的博客形态的静态站点生产机器。它有一个模版目录，其中包含原始文本格式的文档，通过一个转换器（如 [Markdown](http://daringfireball.net/projects/markdown/)）和我们的 [Liquid](https://github.com/Shopify/liquid/wiki) 渲染器转化成一个完整的可发布的静态网站，你可以发布在任何你喜爱的服务器上。Jekyll 也可以运行在 [GitHub Page](http://pages.github.com/) 上，也就是说，你可以使用 GitHub 的服务来搭建你的项目页面、博客或者网站，而且是**完全免费**的。

## 安装

### 事先准备

安装 Jekyll 相当简单，但是你得先做好一些准备工作。开始前你需要确保你在系统里已经有如下配置。

- [Ruby](http://www.ruby-lang.org/en/downloads/)（including development headers, Jekyll 2 需要 v1.9.3 及以上版本，Jekyll 3 需要 v2 及以上版本）
- [RubyGems](http://rubygems.org/pages/download)
- Linux, Un ix, or Mac OS X
- [NodeJS](http://nodejs.org), 或其他 JavaScript 运行环境（Jekyll 2 或更早版本需要 CoffeeScript 支持）。
- [Python 2.7](https://www.python.org/downloads/)（Jekyll 2 或更早版本）

### 用 RubyGems 安装 Jekyll

安装 Jekyll 的最好方式就是使用 [RubyGems](http://rubygems.org/pages/download). 你只需要打开终端输入以下命令就可以安装了：

```bash
gem install jekyll
```

所有的 Jekyll 的 gem 依赖包都会被自动安装，所以你完全不用去担心。如果你在安装中碰到了问题，请查看 [troubleshooting](https://jekyllcn.com/docs/troubleshooting/) 或者 [report an issue](https://github.com/jekyll/jekyll/issues/new) 那么 Jekyll 社区就会帮助你解决问题了。

**遇到报错**：[FilePermissionError](相关错误/FilePermissionError.md)错误

## 各工具在Jekyll工作流发挥的作用

```text
开始 Jekyll 项目
    ├── 创建项目：需要 ruby（已安装）
    ├── 管理依赖：需要 bundler（ruby-bundler）
    ├── 编译主题：可能需要 C 扩展（ruby-dev）
    ├── 构建网站：可能需要编译 Sass（build-essential）
    └── 运行服务器：需要所有依赖正确安装
```