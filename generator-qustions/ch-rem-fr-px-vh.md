这些都是CSS中的不同单位，每个都有其特定的用途和特点。让我们逐一解释它们的用法：

1. ch (字符宽度)
   - 定义：1ch 等于当前字体的 "0" 字符的宽度。
   - 用法：常用于设置等宽字体的元素宽度。
   - 示例：
     ```css
     .code-block {
       width: 80ch; /* 宽度为80个字符 */
     }
     ```

2. rem (根元素字体大小)
   - 定义：相对于根元素（通常是 <html>）的字体大小。
   - 用法：常用于响应式设计，易于全局缩放。
   - 示例：
     ```css
     html {
       font-size: 16px;
     }
     .title {
       font-size: 2rem; /* 32px */
     }
     ```

3. fr (弹性单位)
   - 定义：在 CSS Grid 布局中使用，表示剩余空间的一份。
   - 用法：用于创建灵活的网格列和行。
   - 示例：
     ```css
     .grid-container {
       display: grid;
       grid-template-columns: 1fr 2fr 1fr; /* 三列布局，中间列占用两倍空间 */
     }
     ```

4. px (像素)
   - 定义：屏幕上的一个点。
   - 用法：用于精确控制大小，但不利于响应式设计。
   - 示例：
     ```css
     .button {
       padding: 10px 20px;
       border-radius: 5px;
     }
     ```

5. vh (视口高度)
   - 定义：视口高度的 1%。
   - 用法：常用于创建全屏布局或相对于视口大小的元素。
   - 示例：
     ```css
     .full-screen {
       height: 100vh; /* 全屏高度 */
     }
     .half-screen {
       height: 50vh; /* 半屏高度 */
     }
     ```

比较和使用场景：

1. 响应式设计：
   - rem 用于整体布局和字体大小
   - vh 用于与视口相关的尺寸

2. 精确控制：
   - px 用于边框、小图标等需要精确像素的场景

3. 文本相关：
   - ch 用于控制文本宽度，特别是等宽字体

4. 灵活布局：
   - fr 用于 CSS Grid 中创建灵活的列和行

5. 组合使用：
   ```css
   .container {
     width: 90%;
     max-width: 1200px;
     margin: 0 auto;
     padding: 2rem;
   }

   .hero {
     height: 80vh;
     font-size: 1.2rem;
   }

   .grid {
     display: grid;
     grid-template-columns: 1fr 2fr 1fr;
     gap: 20px;
   }
   ```

这个例子展示了如何组合使用这些单位来创建一个响应式的布局。

选择合适的单位取决于你的设计需求和目标设备。在现代Web开发中，通常会混合使用这些单位以实现最佳的布局和响应式效果。