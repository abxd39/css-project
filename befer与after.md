":before"和":after"是CSS伪元素,而不是HTML属性。它们用于在元素的内容之前或之后插入内容,而无需修改HTML结构。正确的书写方式是"::before"和"::after"(CSS3语法),但":before"和":after"(CSS2语法)也被广泛支持。

这里是一个简单的例子来说明它们的用法:



```html
<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <title>::before和::after示例</title>
    <style>
        .example::before {
            content: "之前 ";
            color: blue;
        }
        .example::after {
            content: " 之后";
            color: red;
        }
    </style>
</head>
<body>
    <p class="example">这是主要内容</p>
</body>
</html>

```

在这个例子中:

1. `.example::before` 会在元素内容之前添加蓝色的"之前"文本。
2. `.example::after` 会在元素内容之后添加红色的"之后"文本。

这些伪元素的主要特点是:

1. 它们不会出现在DOM中,只在CSS中定义。
2. 可以用来添加装饰性内容,而不影响文档的语义结构。
3. 可以设置各种CSS属性,如颜色、字体、背景等。
4. 必须使用`content`属性来指定要插入的内容。

这些伪元素在网页设计中非常有用,可以用于添加图标、引号、提示文本等,而无需额外的HTML标记。

您想了解更多关于::before和::after的具体用法吗?或者您有其他相关的问题?