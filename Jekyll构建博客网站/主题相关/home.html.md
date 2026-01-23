```text
本html文件用到了liquid模板，我不是很熟悉这个模板，请针对本文件进行解释
```

下面按“Liquid 在这个布局里做了什么”来拆解解释（文件：​_layouts/home.html）。

**1) 顶部 Front Matter（告诉 Jekyll 这是什么布局）**

- `--- ... ---` 这一段叫 Front Matter。
- `layout: default` 表示：这个页面内容会套在父布局 `default` 里渲染（通常 `default` 会包含全站 `<html> / <head> / <body>` 框架，以及 `{{ content }}` 插槽）。

**2) 输出站点全局变量：`site.*`**
```html
<h1 class="hero-title">{{ site.title | escape }}</h1>
<p class="hero-subtitle">{{ site.description | escape }}</p>
```
- `{{ ... }}`：**输出表达式**（把变量渲染成文本）。
- `site.title` / `site.description`：来自 [_config.yml](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) 的站点配置。
- `| escape`：Liquid 的 **过滤器 filter**，把特殊字符转义成 HTML 安全形式（例如 `<` 变 `&lt;`），避免破坏页面结构或注入问题。

**3) 遍历文章列表：`for post in site.posts`**
```html
{%- for post in site.posts -%}
  ...
{%- endfor -%}
```
- `{% ... %}`：**逻辑标签**（控制流程，不直接输出文本）。
- `site.posts`：Jekyll 自动收集 [_posts](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) 里的文章，按时间倒序排列。
- `post`：循环变量，代表当前文章对象（有 `post.title`、`post.url`、`post.date` 等）。
- `{%-` 和 `-%}`：**空白控制**。`-` 会吞掉标签前/后的空白和换行，让生成的 HTML 更紧凑（不影响浏览器渲染，只影响源码“好不好看/是否有多余空行”）。

**4) 条件渲染：`if post.image`、`if post.excerpt` 等**
```html
{%- if post.image -%}
  <img src="{{ post.image | relative_url }}" ...>
{%- endif -%}
```
- `if post.image`：当文章的 Front Matter 里定义了 `image: ...` 才输出图片块。
- `relative_url`：把路径按站点的 `baseurl` 等设置转换成“正确的相对 URL”。例如你部署在子目录时（`baseurl: /blog`）它会自动补上前缀。
```html
{%- if post.excerpt -%}
  <p>{{ post.excerpt | strip_html | truncate: 100 }}</p>
{%- endif -%}
```
- `post.excerpt`：Jekyll 可能自动生成摘要，或由你用 excerpt 分隔符控制。
- `strip_html`：去掉摘要里的 HTML 标签（避免摘要里出现未闭合标签影响卡片布局）。
- `truncate: 100`：截断到 100 字符左右并加省略号（Liquid 的默认行为）。

**5) 日期输出：机器可读 + 人类可读**
```html
<time datetime="{{ post.date | date_to_xmlschema }}">
  {{ post.date | date: site.date_format }}
</time>
```
- `date_to_xmlschema`：把日期转成 ISO8601（适合 `datetime` 属性，利于 SEO/机器解析）。
- `date: site.date_format`：按你在 [_config.yml](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html) 里配置的 `date_format` 渲染显示样式（例如 `"%Y-%m-%d"`）。

**6) 分类显示：只取第一个分类**
```html
{%- if post.categories.size > 0 -%}
  <span>{{ post.categories | first }}</span>
{%- endif -%}
```
- `post.categories`：文章的分类数组（来自文章 Front Matter 的 `categories`）。
- `.size > 0`：数组非空才显示。
- `| first`：只展示第一个分类（所以如果你有多个分类，这里只会露出一个）。

**7) 链接与 URL：`post.url | relative_url`**
```html
<a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
```
- `post.url`：Jekyll 生成的文章链接路径（与 permalink 规则有关）。
- 再次用 `relative_url`：确保在不同部署路径下链接仍正确。
- `post.title | escape`：同理，标题做 HTML 转义更安全稳妥。

如果你愿意，我可以顺手结合你的 [_config.yml](vscode-file://vscode-app/usr/share/code/resources/app/out/vs/code/electron-browser/workbench/workbench.html)（比如 `baseurl`、`date_format`、permalink）举一个“某篇 post 的变量实际会渲染成什么 HTML”的具体例子，帮助你把这些 Liquid 变量和最终页面对应起来。