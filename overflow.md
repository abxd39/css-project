CSS 中的 overflow 属性用于指定当内容溢出元素框时发生的情况。它有以下几个可用的值：

visible：默认值。内容不会被裁剪，会呈现在元素框之外。
hidden：内容会被裁剪，并且其余内容是不可见的。
scroll：内容会被裁剪，但提供滚动条以查看其余内容。
auto：如果内容被裁剪，则浏览器会显示滚动条以查看其余内容。
clip：CSS Overflow Module Level 3 中的一个实验性值，作用类似于 hidden，但是它允许对不同的方向指定不同的行为。
overlay：类似于 scroll，但滚动条会覆盖在内容上。这个值在新的规范中不推荐使用。
此外，overflow 属性可以分为 overflow-x 和 overflow-y，分别用于控制元素的水平方向和垂直方向的溢出行为。这意味着你可以单独控制元素的水平或垂直溢出，例如：

overflow-x: auto;：只在水平方向上根据需要显示滚动条。
overflow-y: scroll;：总是在垂直方向上显示滚动条，即使所有内容都可见。