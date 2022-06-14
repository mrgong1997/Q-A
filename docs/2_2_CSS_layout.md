>

### 1.常见的CSS布局单位

---

#### Answer：

- px ：一般指的是 CSS像素
- % ：一般指的是相对于父元素
- em/rem ：em 相对于父元素，rem 相对于根元素 （默认 font-size 为16px）
- vw/vh ：相对于视图窗口的宽度/高度，视窗宽度高度都为 100

---

### 2.水平垂直居中的实现

---

#### Answer：

法一：**flex 布局**(最简单)

```
.parent {
    display: flex;
    justify-content:center;
    align-items:center;
}
```

法二：**绝对定位之 margin：auto**（适合父元素有宽高情况）

```
.parent {
    position: relative;
}
 
.child {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto; // 四个方向设为0，并将 margin 占据所有可用空间
}

```

法三：**绝对定位之 margin-top/left 设为负**（适合子元素宽高）

```
.parent {
    position: relative;
}
 
.child {
    position: absolute;
    top: 50%;
    left: 50%;
    margin-top: -50px;     /* 自身 height 的一半 */
    margin-left: -50px;    /* 自身 width 的一半 */
}

```

---















>   参考链接：[「2021」高频前端面试题汇总之CSS篇 - 掘金](https://juejin.cn/post/6905539198107942919)