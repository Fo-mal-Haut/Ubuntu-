## 自动安装 Ruby

如果您的计算机已经连接到 Internet，那么最简单安装 Ruby 的方式是使用 **yum** 或 **apt-get**。在命令提示符中输入以下的命令，即可在您的计算机上安装 Ruby。
```Shell
sudo apt-get install ruby-full # Debian 或 Ubuntu 系统
```

**安装结果**：安装过程飞快，原因在于Ruby 是 Linux 生态的重要工具，许多 Linux 系统工具和包管理器（如 `apt` 的部分组件）用 Ruby 编写。

# 安装必要工具与介绍
```Shell
# 安装必要的工具 
sudo apt install ruby-bundler ruby-dev build-essential
```
## **1. `ruby-bundler` - Ruby 的依赖管理工具**
- **Bundler** 是 Ruby 的**包管理器**，类似于：
    - Node.js 的 `npm` / `yarn`
    - Python 的 `pip` / `poetry`
    - PHP 的 `composer`

**主要功能：**

- 管理项目的 gem 依赖
- 确保不同环境下使用相同的 gem 版本
- 解决 gem 之间的依赖冲突

**常用命令**：
```Shell
# 安装 Gemfile 中指定的所有 gems
bundle install

# 更新 gems
bundle update

# 执行命令时使用 bundle 管理的 gems
bundle exec jekyll serve

# 查看已安装的 gems
bundle list
```

## **2. `ruby-dev` - Ruby 开发头文件和工具**

- 包含编译 Ruby **原生扩展**（C 扩展）所需的：**头文件**（.h 文件）、 **静态库**、**开发工具链接口**

## **3. `build-essential` - 基本编译工具套件**

这是**编译任何软件**的基础工具包、包含 GNU 编译器集合和基础构建工具

