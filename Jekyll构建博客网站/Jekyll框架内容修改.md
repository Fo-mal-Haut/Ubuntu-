# 1.  [更改标题和说明](https://docs.github.com/zh/pages/quickstart#changing-the-title-and-description)

**参考资料**：可以参阅Jekyll官方文档[配置](https://jekyllcn.com/docs/configuration/)

在jekyll中，标题和说明等信息都保存在文件`_config.yml`里面，相关设置案例如下：

```Yml
# 博客基本信息

title: # 记录本博客的标题
email: # 作者的邮件地址

baseurl: "/Jekyll" # the subpath of your site, e.g. /blog
url: "https://fo-mal-haut.github.io" # the base hostname & protocol for your site, e.g. http://example.com

twitter_username: # 社交媒体账号，这是Minima主题自带的配置，包含许多社交媒体
github_username:  # 会自动显示图标

# 时间信息
date_format: "%Y-%m-%d"  # 日期格式
timezone: Asia/Shanghai   # 时区
```

`_config.yml`文件比较特殊，在`bundle exec jekyll serve`自动构建过程中，修改本配置文件不会立即生效，需要重新搭建站点才可生效。

# 2.了解[关于 Jekyll 站点中的内容](https://docs.github.com/zh/pages/setting-up-a-github-pages-site-with-jekyll/adding-content-to-your-github-pages-site-using-jekyll#about-content-in-jekyll-sites)

## 2.1 Front Matter（前页、头信息）

**参考资料**：有关详细信息，请参阅 Jekyll 文档中的[front matter](https://jekyllrb.com/docs/front-matter/)或者[头信息](https://jekyllcn.com/docs/frontmatter/)。

**头信息**的作用：为站点建立提供必要信息，例如所有的博客文件可以用 [Markdown](http://daringfireball.net/projects/markdown/) 编写，也可以用 [Textile](http://textile.sitemonks.com/) 格式编写。只要文件中有 [YAML 头信息](https://jekyllcn.com/docs/frontmatter/)，它们就会从源格式转化成 HTML 页面，从而成为你的静态网站的一部分。

要为网站上的页面或帖子设置变量和元数据，例如标题和布局， 可以将 YAML 前页添加到任意 Markdown 或 HTML 文件的顶部，并且用虚线隔离出顶部内容，例如：
```yaml
---
layout: post
title: Blogging Like a Hacker
---
```
前页设置的变量分为两种：**预定义全局变量**和**自定义变量**，以下会介绍预定义变量的作用以及自定义变量的应用方式。

**预定义全局变量**：

| 变量名称        | 描述                                                                                         |
| ----------- | ------------------------------------------------------------------------------------------ |
| `layout`    | 如果设置的话，会指定使用该**模板文件**。指定模板文件时候不需要文件扩展名。模板文件必须放在 `_layouts` 目录下。                            |
| `permalink` | 如果你需要让你发布的博客的 URL 地址**不同于默认值** `/year/month/day/title.html`，那你就设置这个变量，然后变量值就会作为最终的 URL 地址。 |
| `published` | 如果你不想在站点生成后展示某篇特定的博文，那么就设置（该博文的）该变量为 false。                                                |

**自定义变量**：

在头信息中没有预先定义的任何变量，都会在数据转换中通过 **Liquid 模板**被调用。
例如，如果你设置一个 title 变量，然后你就可以在你的模板中使用这个 title 变量，来设置页面的标题（title）：
```html
<!DOCTYPE HTML>
<html>
  <head>
    <title>{{ page.title }}</title>
  </head>
  <body>
    ...
```

## 2.2 内容(pages)和帖子(posts)

**参考资料**：内容请参阅 Jekyll 文档中的[pages](https://jekyllrb.com/docs/pages/)或者[页面](https://jekyllcn.com/docs/pages/)；帖子请参阅[posts](https://jekyllrb.com/docs/posts/)或[博客](https://jekyllcn.com/docs/posts/)

Jekyll 站点中内容的主要类型是**页面**和**帖子**，在后面我会尝试更新页面和帖子。

页面是指与某个特定日期没有关联的**独立内容**，例如“关于”页面。 默认的 Jekyll 站点包含一个名为 `about.md` 的文件，在搭建过程中`.md`格式文件会自动转换为`.html`文件。因此在该文件在 `YOUR-SITE-URL/about.html` 呈现为站点上的一个页面。 
可以编辑该文件的内容以个性化“关于”页面，也可以使用“关于”页作为模板创建新页面。


帖子是**博客文章**。 默认 Jekyll 站点包含名为 `_posts` 的目录，其中包含默认帖子文件。 您可以编辑该帖子的内容，也可以将默认帖子用作模板来创建新帖子。

## 2.3 布局和样式

**参考资料**：有关详细信息，请参阅[关于 GitHub 页面和 Jekyll](https://docs.github.com/zh/pages/setting-up-a-github-pages-site-with-jekyll/about-github-pages-and-jekyll#themes)以及官方文档[Jekyll中的主题](https://jekyllcn.com/docs/themes/)

主题包括**默认布局**和**样式表**。我选用的依旧是Jekyll的默认主题[Minima](https://github.com/jekyll/minima)

它们将自动应用到站点上的新页面和帖子，但您可以覆盖其中任何默认值。并且Jekyll有一个强大的主题系统，可以通过社区的模板和样式来定制自己的站点。Jekyll 主题打包了布局文件、包含文件及样式表。

**安装主题**：

1. 若要安装一套主题，请先将该主题添加到您站点的 `Gemfile` 中：
```
gem 'my-awesome-jekyll-theme'
```
2. 保存并应用 `Gemfile` 中相关的文件变化。
3. 执行命令行 `bundle install` 来安装主题。
4. 最后, 向您站点的 `_config.yml` 中加入下列代码来启用主题：
```
theme: my-awesome-jekyll-theme
```

**主题来源**：

1. Github Pages上支持了部分主题，请参阅 GitHub Pages 站点中的[支持的主题](https://docs.github.com/zh/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll#supported-themes)

2. 同时可以手动添加社区作者创建的主题，例如若要使用 GitHub 上托管的任何其他开放源代码 Jekyll 主题，可以手动添加主题。有关详细信息，请参阅 [GitHub 上托管的主题](https://github.com/topics/jekyll-theme)，“[使用 Jekyll 向 GitHub Pages 站点添加主题](https://docs.github.com/zh/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)”。

3. 同时，也可以自定义一个Jekyll主题，参见官方文档：[创建一套主题](https://jekyllcn.com/docs/themes/#创建一套主题 "Permalink")

## 2.3.1 自定义Minima主题的CSS和HTML：

这些说明非常适用于 GitHub Pages 官方支持的主题。 有关支持的主题的完整列表，请参阅 GitHub Pages 站点上的[支持的主题](https://docs.github.com/zh/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll#supported-themes)。

由于本项目安装的Minima主题是minima-2.5.1版本，因此参考文档为[Minima 2.5.0官方README](https://github.com/jekyll/minima/blob/v2.5.0/README.md).

**布局文件（Layouts）**  
指`_layouts`目录中的文件，用于定义主题的页面结构。

- **default.html** — 基础布局，为其他布局提供框架。衍生布局通过FrontMatter声明`layout: default`关联到此文件，并将自身内容注入到`{{ content }}`标记所在的行。
    
- **home.html** — 用于**首页/着陆页/索引页**的布局。
    
- **page.html** — 用于包含FrontMatter但**不是文章**的文档布局。
    
- **post.html** — 用于**文章**的布局。
    

---

**包含文件（Includes）**  
指`_includes`目录中的代码片段，可插入到同一主题内的多个布局（或其他包含文件）中。

- **disqus_comments.html** — 用于插入Disqus评论框的代码。
    
- **footer.html** — 定义网站的**页脚部分**。
    
- **google-analytics.html** — 插入Google Analytics统计模块（**仅在生产环境生效**）。
    
- **head.html** — 在默认布局中定义`<head></head>`部分的代码块。
    
- **header.html** — 定义网站的**主标题区域**。默认情况下，具有`title`属性的页面会在此显示链接。

---

1. 在 GitHub 上，导航到站点的仓库。

2. 导航到站点的发布来源。 有关详细信息，请参阅“[配置 GitHub Pages 站点的发布源](https://docs.github.com/zh/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)”。

3. 创建名为 `/assets/css/style.scss` 的新文件。

4. 在文件顶部添加以下内容：

```scss
---
---

@import "{{ site.theme }}";
```

5. 在 `@import` 行的后面直接添加所需的任何自定义 CSS 或 Sass（包括导入）。

---

1. 在 GitHub 上，导航到主题的源仓库。 例如，Minimal 的源存储库为 `https://github.com/pages-themes/minimal`。
2. 在 `_layouts` 文件夹中，导航到主题的 `_default.html` 文件。
3. 复制该文件的内容。
4. 在 GitHub 上，导航到站点的仓库。
5. 导航到站点的发布来源。 有关详细信息，请参阅“[配置 GitHub Pages 站点的发布源](https://docs.github.com/zh/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)”。
6. 创建名为 `_layouts/default.html` 的文件。
7. 粘贴之前复制的默认布局内容。
8. 根据需要自定义布局。