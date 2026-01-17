按下F12查看CSS文件能否成功加载：
![](assets/github%20pages构建Jekyll框架站点/file-20260117144113939.png)
**情况描述**：CSS文件无法加载，和上次情况略有不同（上次修改了URL之后，能够成功加载，但是还是没有格式显示）

**AI工具询问**：

是Claude Code + Minimax的方案
```text
❯ 我按照github pages的官方文档，尝试在本地构建Jekyll创建的站点，并并部署到Github Pages上 。全部操作都按照官方文档生成了站点，在本地运行构建成功，但是在github Pages上却只有纯HTML页面，没有CSS格式。为什么会这样？
```

```text
● 找到问题原因了！这是一个 GitHub Pages 部署 Jekyll 时的常见问题。

  你的站点使用 minima 主题，CSS 样式应该来自这个主题。但 GitHub Pages 上样式丢失主要有以下几个原因：

  1. baseurl 配置缺失

  这是最可能的原因。如果你的仓库不是 username.github.io 格式（即用户/组织页面），而是项目页面，那么需要设置 baseurl 为仓库名。

  解决方法：编辑 _config.yml，添加正确的配置：
```

![](assets/github%20pages格式无法正常加载/file-20260117144316599.png)
**问题解决**：仅仅是修改了BaseURL和URL就成功解决了问题