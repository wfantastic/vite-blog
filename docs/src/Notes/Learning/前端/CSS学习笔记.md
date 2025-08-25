---
title: "CSS"
outline: deep
desc: "CSS学习笔记"
tags: "前端"
updateTime: "2025-08-22 19:30"
---

## CSS学习笔记

### CSS的四种引入方式

内联、嵌入、链接、导入
内联：将CSS直接写在HTML元素的`style`属性中。这种方式适用于快速测试或者对单个元素进行样式设置，但不利于维护和复用，因为它会使HTML代码变得冗长。例如：

```html
<div style="color: red;">这是一个红色的文本。</div>
```

嵌入：是在HTML文档的`<head>`部分，使用`<style>`标签直接编写CSS代码。例如：

```html
<head>
  <style>
    .text-red { color: red; }
  </style>
</head>
```

链接：通过HTML的`<link>`标签引入外部的CSS文件。

```html
<head>
<link rel="stylesheet" type="text/css" href="style.css">
</head>
```

导入：在CSS文件或`<style>`标签中使用`@import`规则引入外部CSS文件。虽然导入方式也可以引入外部CSS文件，但它存在一些限制，如必须放在CSS文件的开头，且在旧版浏览器中可能不被支持。

```html
@import url('style.css');
```

### 介绍一下CSS的盒子模型

在HTML页面中的所有元素都可以看成是一个盒子。
盒子的组成有：内容，内边距，边框，外边距。

```plain
CSS的盒子模型有哪些：标准盒子模型、IE盒子模型
CSS的盒子模型区别：
    标准盒子模型：margin、border、padding、content
    IE盒子模型 ：margin、content（ border +  padding  + content ）
通过CSS如何转换盒子模型：
    box-sizing: content-box;/*标准盒子模型*/
    box-sizing: border-box;/*IE盒子模型*/
```

### CSS优先级算法如何计算？

CSS的三大特性：层叠，继承（子元素可以继承父元素的样式），优先级。
优先级比较：
>!important > 内联样式（行内>嵌入、外链） > id > class/伪类/属性 > 标签/伪元素/后代(空格) >子代(>)/相邻>通配 > 继承

### CSS选择符有哪些？哪些属性可以继承？

```plain
1. CSS选择符：
    通配（*）
    id选择器（#）
    类选择器（.）
    标签选择器（div、p、h1...）
    相邻选择器(+)
    后代选择器(ul li)
    子元素选择器（ > ）
    属性选择器(a[href])
    并集选择器(选择器1,选择器2)
    交集选择器(选择器1选择器2)
2. 可以继承：
        1. font 相关属性：font-size、font-weight、line-height。
        2. color：控制文本颜色。
        3. text 相关属性：text-align、text-decoration、letter-spacing、word-spacing。
        4. visibility：控制元素是否可见。
        5. cursor：指定鼠标悬停在元素上时的光标样式。
        6. list-style 相关属性：包括 list-style-type、list-style-position、list-style-image。
        
3. 不可继承属性：border、padding、margin...
```

### 如何用CSS画一个三角形

```html
用边框画（border）,例如：
{
  width: 0;
  height: 0;

  border-left:100px solid transparent;
  border-right:100px solid transparent;
  border-top:100px solid transparent;
  border-bottom:100px solid #ccc;
}
linear-gradient
.triangle {
  width: 160px;
  height: 200px;
  outline: 2px solid skyblue;
  background-repeat: no-repeat;
  background-image: linear-gradient(32deg, orangered 50%, rgba(255, 255, 255, 0) 50%), linear-gradient(148deg, orangered 50%, rgba(255, 255, 255, 0) 50%);
  background-size: 100% 50%;
  background-position: top left, bottom left;
}

clip-path
.triangle{
  margin: 100px;
  width: 160px;
  height: 200px;
  background-color: skyblue;
  clip-path: polygon(0 0, 0% 100%, 100% 50%);
}
```

### 单行文本溢出

在 CSS 中，当单行文本内容超出其容器的宽度时，可以通过设置 overflow 属性来处理文本溢出的情况。常用的方法包括使用 white-space 和 text-overflow 属性。

```css
div{
    width: 200px; /* 容器宽度 */
    white-space: nowrap; /* 不换行 */
    overflow: hidden; /* 超出部分隐藏 */
    text-overflow: ellipsis; /* 溢出部分显示省略号 */
}
```

### 多行文本溢出

处理多行文本溢出的情况相对复杂一些，但也可以通过 CSS 来实现。常用的方法是结合 display: -webkit-box;、-webkit-line-clamp 和 overflow: hidden;。

```css
.text-container {
    display: -webkit-box; /* 使用弹性盒子布局 */
    -webkit-box-orient: vertical; /* 垂直方向排列 */
    -webkit-line-clamp: 3; /* 限制显示行数 */
    overflow: hidden; /* 超出部分隐藏 */
}

/* 兼容性处理 */
.text-container {
    display: -webkit-box;
    display: -webkit-webkit-flex;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
}
```
