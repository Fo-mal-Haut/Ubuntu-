**参考资料**：[一篇完整的 Scss 学习指南，看这篇就够啦](https://blog.csdn.net/Ed7zgeE9X/article/details/123058868), [SASS官方文档](https://sass-lang.com.cn/documentation/), [SASS菜鸟教程](https://www.runoob.com/sass/sass-tutorial.html)

Sass (英文全称：Syntactically Awesome Stylesheets) 是一个最初由 Hampton Catlin 设计并由 Natalie Weizenbaum 开发的层叠样式表语言。

Sass 是一个 CSS 预处理器，也是 CSS 扩展语言，可以帮助我们减少 CSS 重复的代码，节省开发时间，并且完全兼容所有版本的 CSS。他能生成良好格式化的 CSS 代码，易于组织和维护。

Sass 文件后缀为 .scss。

## 为什么使用 Sass?

CSS 本身语法不够强大，导致重复编写一些代码，无法实现复用，而且在代码也不方便维护。

Sass 引入合理的样式复用机制，增加了规则、变量、混入、选择器、继承、内置函数等等特性。

我们可以举个例子，我们会在 CSS 中重复使用很多次十六进制的颜色代码，当有了变量之后，如果要改变颜色代码，只要修改变量的值就好了：
```SCSS
/* 定义颜色变量，要修改颜色值，修改这里就可以了 */
$primary_1: #a2b9bc;
$primary_2: #b2ad7f;
$primary_3: #878f99;

/* 使用变量 */
.main-header {
  background-color: $primary_1;
}

.menu-left {
  background-color: $primary_2;
}

.menu-right {
  background-color: $primary_3;
}
```

## Scss和Sass

`Sass`从第三代开始，放弃了缩进式风格，并且完全向下兼容普通的`CSS`代码，这一代的`Sass`也被称为`Scss`。

## Sass 是如何工作的？

浏览器并不支持 Sass 代码。因此，你需要使用一个 Sass 预处理器将 Sass 代码转换为 CSS 代码。