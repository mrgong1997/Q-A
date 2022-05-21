>
<!-- 5.11-5.15  -->
### 1.CSS3 中有哪些新特性

---

#### Answer：

- 文字特效 （text-shadow）和文字渲染 （Text-decoration）
- 边框属性：圆角（border-radius）、阴影（box-shadow）、图片（border-image）
- 多列布局（multi-column layout）
- 渐变（gradient）
- 变换（transform）、过渡（transition）、动画（animation）

---

### 2.CSS 选择器的优先级

---

#### Answer：

!important > style 1000 > id 100 > class （属性、伪类）10 > 标签（伪元素） 1 > (后代选择器) 0

---

### 3.CSS 中有哪些可继承与不可继承属性

---

#### Answer：

可继承：  
- 字体属性（font-xxx）
- 文本属性（text-align、letter-spacing、color）
- visibility 

不可继承：
- 盒模型属性（width、margin、padding、border 等）
- 定位属性 （display、float、top 等）
- 背景属性（background-xxx）

---

### 4.说说 CSS 的盒模型

---

#### Answer：

标准盒模型（box-sizing: content-box）：宽高只包含 content  

替代盒模型（box-sizing: border-box）：宽高还包括padding 和 border

---

### 5.display 的 block、inline 和 inline-block 的区别

---

#### Answer：

block：独占一行可设置宽高  

inline：不独占一行不可设宽高（只能设置**水平**方向的 margin/padding）

inline-block：既不独占一行也可设置宽高 （两者优势结合）

---

### 6.display: none、visibility: hidden、opacity: 0 优劣和适用场景

---

#### Answer：

|        |  DOM |  事件监听  | 继承  | 性能  |
|  ----  | ----  | ----  | ----  | ----  |
| display: none  | 直接不渲染，因此不占空间 | 因此无法监听 | 更无法继承（根本无子元素） | 改变属性会导致重排，性能消耗大 |
| visibility: hidden  | 渲染但不可见，占空间 | 无法监听 | 子元素继承，且可通过改变属性取消隐藏 | 重绘，性能消耗较少 |
| opacity: 0  | 渲染但不可见，占空间 | 可以监听 | 子元素继承，不可通过改变属性取消隐藏 | 重绘，性能消耗较少 |

总结 摆烂层级：display: none （不渲染） > visibility: hidden(渲染不监听) > opacity: 0 (渲染且监听)  

其它隐藏元素的方法：  
- position: absolute + top 等；移出可视区域
- z-index:负值；被其他元素遮盖
- transform: scale(0,0)；把元素缩放至 0 实现隐藏

---

### 7.link 和 @import 的区别

---

#### Answer：

- 作用不同：link 可加载 css、rel 等多种属性；@import 只能加载 css  
- 加载顺序不同：link 和页面同时加载；@import 等页面加载完后才能加载  
- 兼容问题：link不存在兼容问题；@import 在 ie5 以上才兼容  

总结： link 优于 @import

---

### 8.transition 和 animation 的区别

---

#### Answer：

- transition：实现需要触发事件，只设置一个开始关键帧和一个结束关键帧
- animation：实现不需要触发事件（可自己执行且循环），可以设置多个关键帧

---

### 9.为什么有时候用 translate 来改变位置而不是定位

---

#### Answer：

translate 是 transform 属性的一个值。改变 transform 不会触发浏览器回流和重绘，只会触发复合（compositions）；而改变绝对定位会。

---

### 10.li 元素之间的空白间隔是什么原因引起的？如何解决？

---

#### Answer：

浏览器会把行内元素间的空白字符（空格、换行等）渲染成空格。  
书写代码时通常把 li 元素单独写一行，导致出现空格。

解决方法：
- 把 li 写同一行（不美观）
- 把 ul 的 font-size:0 （其他字符也会被设为0，需重设其他的）
- 把 ul 的 letter-spacing:-8px（li 元素需要设为默认的 letter-spacing:normal）

---

### 11.替换元素的概念及计算规则

---

#### Answer：

替换元素概念：通过修改某个属性值就能替换内容的元素（如 img input textarea 等）  

计算规则：
CSS 尺寸（只设置宽度则按原比例缩放） > HTML 尺寸 > 固有尺寸(图片/视频原本尺寸) > 300px * 150px

---


### 12.

---

#### Answer：



---









>   参考链接：[「2021」高频前端面试题汇总之CSS篇 - 掘金](https://juejin.cn/post/6905539198107942919)