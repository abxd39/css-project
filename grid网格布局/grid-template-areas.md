
grid 布局的直接对象--第一个字元素，

使用 grid-template-areas 保证基本的格调。
以移动端优先做一个考虑的一个出发点；

首先应该是从我们最小的尺寸开始定义我们的网格布局，然后在增加媒体查询，适应不同的屏幕。

```css
.grid{


grid-template-areas:"one two three " "one two four";
}
```