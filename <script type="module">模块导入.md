
`<script type="module">` 是一种在HTML中引入JavaScript模块的方式。这个属性告诉浏览器该脚本应该被视为一个JavaScript模块，而不是传统的脚本。使用模块有几个重要的特点和优势：

1. 模块作用域：
   - 模块中定义的变量和函数默认不会污染全局作用域。
   - 每个模块都有自己的作用域。

2. 导入和导出：
   - 可以使用 `import` 和 `export` 语句在模块间共享代码。

3. 严格模式：
   - 模块自动运行在严格模式下，不需要显式声明 `"use strict"`。

4. 延迟执行：
   - 模块脚本默认是延迟加载的（类似于 `defer` 属性），会等到HTML解析完成后才执行。

5. 只执行一次：
   - 无论一个模块被导入多少次，它只会被执行一次。

6. 支持顶层 `await`：
   - 在模块的顶层可以直接使用 `await`，而不需要包装在异步函数中。

示例：

HTML文件：
```html
<!DOCTYPE html>
<html>
<head>
    <title>Module Example</title>
</head>
<body>
    <script type="module" src="main.js"></script>
</body>
</html>
```

main.js：
```javascript
import { sayHello } from './greetings.js';

sayHello('World');
```

greetings.js：
```javascript
export function sayHello(name) {
    console.log(`Hello, ${name}!`);
}
```

使用注意事项：

1. CORS 限制：
   - 模块脚本受到跨源限制，通常需要通过 HTTP 服务器加载，而不是直接打开 HTML 文件。

2. 浏览器支持：
   - 现代浏览器普遍支持模块，但旧版浏览器可能不支持。

3. 路径问题：
   - 导入路径需要是完整的相对路径或绝对路径，不能省略文件扩展名。

4. 异步特性：
   - 模块的加载是异步的，这可能影响执行顺序。

5. 不支持内联模块：
   - `type="module"` 通常用于外部脚本文件，不建议用于内联脚本。

使用模块可以帮助更好地组织和管理代码，特别是在大型项目中。它提供了一种结构化和封装代码的方式，使得代码更易于维护和重用。