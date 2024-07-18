### CSS 

### grid布局注意事项。 在什么情况下会失效？
### CSS 属性失效的情景分析。
### CSS 优先级，覆盖，失效的情况？ 

CSS的优先级、覆盖和失效是前端开发中常见的问题。让我们逐一探讨这些情况：

1. CSS 优先级

CSS 优先级决定了在发生样式冲突时，哪个样式会被应用。优先级从高到低排序如下：

a) !important 声明
b) 内联样式（style 属性）
c) ID 选择器 (#id)
d) 类选择器 (.class)、属性选择器 ([attr])、伪类 (:hover)
e) 元素选择器 (div, p)、伪元素 (::before)
f) 通用选择器 (*)

此外：
- 更具体的选择器优先级更高
- 相同优先级的样式，后面的会覆盖前面的

2. CSS 覆盖情况

CSS 覆盖发生在：

a) 相同选择器，后面的样式覆盖前面的
b) 更高优先级的选择器覆盖低优先级的
c) 使用 !important 可以覆盖其他样式（但应谨慎使用）
d) 内联样式通常会覆盖外部样式表中的样式

3. CSS 失效的情况

CSS 可能在以下情况下失效：

a) 选择器错误或拼写错误
b) 优先级被其他样式覆盖
c) 继承问题（某些属性不会被子元素继承）
d) 浏览器兼容性问题
e) 样式应用到了错误的元素
f) 使用了未闭合的注释
g) 样式表未正确链接到 HTML 文件
h) 使用了不正确的单位或值

避免 CSS 失效的建议：

1. 使用开发者工具检查元素的实际应用样式
2. 确保选择器的正确性和具体性
3. 了解并合理使用 CSS 优先级规则
4. 注意浏览器前缀和兼容性问题
5. 使用 CSS Lint 等工具检查 CSS 代码
6. 保持 CSS 代码的组织和可维护性
7. 适当使用 CSS 重置或标准化

实例：

```css
/* 低优先级 */
p { color: blue; }

/* 高优先级 */
#content p.highlight { color: red; }

/* 最高优先级 */
p { color: green !important; }
```

在这个例子中，即使有更具体的选择器，带有 !important 的样式也会被应用。

您对 CSS 优先级和覆盖规则有什么特别的疑问吗？或者您在实际开发中遇到过哪些相关的问题？

### 常见的CSS选择器  
CSS选择器是用来选择要设置样式的HTML元素的模式。以下是常见的CSS选择器类型及其用法：

1. 基本选择器

   a) 通用选择器：
      * { margin: 0; }

   b) 元素选择器：
      p { color: blue; }

   c) 类选择器：
      .highlight { background-color: yellow; }

   d) ID选择器：
      #header { font-size: 24px; }

   e) 属性选择器：
      [type="text"] { border: 1px solid gray; }

2. 组合选择器

   a) 后代选择器（空格）：
      div p { margin-bottom: 10px; }

   b) 子元素选择器（>）：
      ul > li { list-style-type: square; }

   c) 相邻兄弟选择器（+）：
      h1 + p { font-weight: bold; }

   d) 通用兄弟选择器（~）：
      h1 ~ p { color: gray; }

3. 伪类选择器

   a) :hover
      a:hover { text-decoration: underline; }

   b) :first-child
      li:first-child { font-weight: bold; }

   c) :nth-child(n)
      tr:nth-child(even) { background-color: #f2f2f2; }

   d) :not()
      input:not([type="submit"]) { border: 1px solid #ccc; }

4. 伪元素选择器

   a) ::before
      .quote::before { content: ""; }

   b) ::after
      .clearfix::after { content: ""; display: table; clear: both; }

   c) ::first-line
      p::first-line { font-variant: small-caps; }

5. 组合使用

   可以组合多个选择器来创建更具体的规则：

   div.container p.highlight { color: red; }

6. 选择器列表

   可以将多个选择器组合在一起，共享相同的样式声明：

   h1, h2, h3 { font-family: Arial, sans-serif; }

7. 属性选择器的变体

   a) [attr^="value"] （以value开头）
      [class^="btn-"] { padding: 5px 10px; }

   b) [attr$="value"] （以value结尾）
      [href$=".pdf"] { background-image: url(pdf-icon.png); }

   c) [attr*="value"] （包含value）
      [class*="col-"] { float: left; }

使用这些选择器的技巧：

1. 保持选择器简洁，避免过度特定化。
2. 利用CSS的级联特性，从通用样式到特定样式。
3. 使用类选择器来定义可重用的样式。
4. 避免过度使用ID选择器，因为它们的特异性很高。
5. 使用属性选择器可以基于元素的特定属性来应用样式。

您对这些选择器有什么特别的问题吗？或者您想了解如何在特定情况下使用某个选择器？

当然,我很乐意为每种选择器类型提供具体的例子。这些例子将帮助你更好地理解每个选择器的用法。

1. 基本选择器

   a) 通用选择器：
      ```css
      * { 
        box-sizing: border-box; 
      }
      ```
      这会将所有元素的盒模型设置为border-box。

   b) 元素选择器：
      ```css
      p { 
        line-height: 1.6; 
      }
      ```
      这会设置所有段落的行高。

   c) 类选择器：
      ```css
      .btn {
        padding: 10px 15px;
        background-color: #007bff;
        color: white;
      }
      ```
      这定义了一个按钮样式类。

   d) ID选择器：
      ```css
      #main-nav {
        position: fixed;
        top: 0;
        width: 100%;
      }
      ```
      这为主导航栏设置了固定定位。

   e) 属性选择器：
      ```css
      [disabled] {
        opacity: 0.5;
        cursor: not-allowed;
      }
      ```
      这会样式化所有禁用的表单元素。

2. 组合选择器

   a) 后代选择器：
      ```css
      .article p {
        text-indent: 1em;
      }
      ```
      这会缩进文章中所有段落的首行。

   b) 子元素选择器：
      ```css
      .nav > li {
        display: inline-block;
      }
      ```
      这会使导航栏的直接子元素li水平排列。

   c) 相邻兄弟选择器：
      ```css
      h2 + p {
        font-size: 1.1em;
        font-weight: bold;
      }
      ```
      这会强调紧跟在h2标题后的段落。

   d) 通用兄弟选择器：
      ```css
      h1 ~ p {
        margin-left: 20px;
      }
      ```
      这会给h1后的所有段落添加左边距。

3. 伪类选择器

   a) :hover
      ```css
      .btn:hover {
        background-color: #0056b3;
      }
      ```
      这会在鼠标悬停时改变按钮的背景色。

   b) :first-child
      ```css
      li:first-child {
        border-top: none;
      }
      ```
      这会移除列表中第一个项目的顶部边框。

   c) :nth-child(n)
      ```css
      tr:nth-child(odd) {
        background-color: #f9f9f9;
      }
      ```
      这会为表格的奇数行添加背景色。

   d) :not()
      ```css
      input:not(:checked) + label {
        color: gray;
      }
      ```
      这会使未选中的复选框的标签变灰。

4. 伪元素选择器

   a) ::before
      ```css
      .quote::before {
        content: "\201C";
        font-size: 2em;
        color: #888;
      }
      ```
      这会在引用前添加一个大的左引号。

   b) ::after
      ```css
      .external-link::after {
        content: "\2197";
        display: inline-block;
        margin-left: 5px;
      }
      ```
      这会在外部链接后添加一个箭头图标。

这些例子展示了各种选择器的实际应用。你可以根据具体需求组合使用这些选择器来创建更复杂的样式规则。有什么特定的样式效果你想了解如何实现吗？

### CSS媒体查询 @media
//当屏幕尺寸大于 600px 时
会破坏代码的流畅性 CSS 有一个替代方案。
```css
@media(min-width:600px){
    .customers-grid{

    }
} 
```
第11集 
- 对齐网格轨道align-content & justify content

### ch rem fr px vh    的用法？
[CSS单位用法和使用情景](/css-project/generator-qustions/ch-rem-fr-px-vh.md)
css 中的display是干嘛的？


CSS Grid 
[第二集： fr单位和repeat()函数](/css-project/grid网格布局/fr单位和repeat()函数/第二集fr单位和repeat()函数.md)

[index.html中导入javascript模块](/css-project/<script%20type="module">模块导入.md)