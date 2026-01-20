**参考文件**：[Jekyll官方文档 主题](https://jekyllcn.com/docs/themes/#覆盖主题默认内容 "Permalink")

Jekyll 主题含有主题默认的布局文件、包含文件和样式表，但您可以使用自己站点的内容去覆盖它们。举个例子，如果您选择使用一个具有 `page` 布局的主题，您能通过在 `_layouts` 文件夹下创建一个属于自己的 `page` 布局文件(例如 `_layouts/page.html`)来覆盖当前主题的布局。

在下列文件夹中，Jekyll 会优先查看您站点中的内容，然后查看主题的默认内容：

- `/assets`
- `/_layouts`
- `/_includes`
- `/_sass`

# 文件说明
以下会分别介绍这四个文件夹的内容，部分内容在[Jekyll框架内容修改](Jekyll框架内容修改.md)，这其中参考了[Minima 2.5.0官方README](https://github.com/jekyll/minima/blob/v2.5.0/README.md).

## `_layouts`文件夹

**布局文件（Layouts）**  
指`_layouts`目录中的文件，用于定义主题的页面结构。

- **default.html** — 基础布局，为其他布局提供框架。衍生布局通过FrontMatter声明`layout: default`关联到此文件，并将自身内容注入到`{{ content }}`标记所在的行。
- **home.html** — 用于**首页/着陆页/索引页**的布局。
- **page.html** — 用于包含FrontMatter但**不是文章**的文档布局。
- **post.html** — 用于**文章**的布局。

## `_includes`文件夹

指`_includes`目录中的代码片段，可插入到同一主题内的多个布局（或其他包含文件）中。

- **disqus_comments.html** — 用于插入Disqus评论框的代码。
- **footer.html** — 定义网站的**页脚部分**。
- **google-analytics.html** — 插入Google Analytics统计模块（**仅在生产环境生效**）。
- **head.html** — 在默认布局中定义`<head></head>`部分的代码块。
- **header.html** — 定义网站的**主标题区域**。默认情况下，具有`title`属性的页面会在此显示链接。

## `_sass`文件夹

指的是位于 `_sass` 目录中的 `.scss` 文件，这些文件定义了主题的样式。

- **`minima.scss`** — 由预处理文件 `main.scss` 导入的核心文件，它定义了主题的变量默认值，并进一步导入 Sass 部分文件来补充自身。
- **`minima/_base.scss`** — 重置并定义各种 HTML 元素的基础样式。
- **`minima/_layout.scss`** — 定义各种布局的视觉样式。
- **`minima/_syntax-highlighting.scss`** — 定义语法高亮的样式。

因此需要去了解sass的内容，内容参阅[sass基本介绍](sass/sass基本介绍.md)
## `assets`文件夹

指的是 `assets` 目录中的各种资源文件。包含 `main.scss` 文件，该文件从 `_sass` 目录导入 Sass 文件。这个 `main.scss` 会被处理成主题的主要样式表 `main.css`，通过 `_includes/head.html` 在 `_layouts/default.html` 中调用。

该目录可以包含子目录来管理同类资源，并将原样复制到最终转换后的站点目录中。