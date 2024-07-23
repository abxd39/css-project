flex-flow 是一个 CSS 属性，它是 flex-direction 和 flex-wrap 这两个属性的简写形式。这个属性用于设置 Flex 容器中子项的排列方向以及是否换行。

flex-direction 控制子项的排列方向，比如行（row）或列（column）。
flex-wrap 控制子项是否可以换行，比如换行（wrap）或不换行（nowrap）。
flex-flow 的语法如下：

.container {
  display: flex;
  flex-flow: row wrap;
}

这里，.container 是一个 Flex 容器，其子项将沿着行方向排列，并且在容器宽度不足以容纳所有子项时会换行。

通过使用 flex-flow 属性，你可以更方便地同时设置子项的排列方向和换行行为，而不是分别设置 flex-direction 和 flex-wrap。