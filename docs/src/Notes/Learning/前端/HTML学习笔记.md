---
title: "HTML"
outline: deep
desc: "HTML学习笔记"
tags: "前端"
updateTime: "2025-07-22 19:30"
---

## HTML考题

### 前端页面有哪三层构成，分别是什么？作用是什么？Web标准的构成

1. HTML（HyperText Markup Language）：结构层，它是网页的基础，用于定义网页的内容结构，如标题、段落、列表、图像等元素。HTML标签告诉浏览器如何组织和呈现这些内容。
2. CSS（Cascading Style Sheets）：样式层，CSS负责为HTML元素添加样式，如颜色、字体、布局、间距等，使得内容具有视觉吸引力并适应不同的设备和屏幕尺寸。通过媒体查询，可以实现响应式设计。
3. JavaScript（JS）：行为层，JavaScript是动态交互的核心，它使网页能够响应用户的操作，执行复杂的逻辑，比如表单验证、动画效果、数据绑定等。现代前端开发还可能用到框架和库（如React、Vue或Angular）来简化开发过程。

### title与h1的区别、b与strong的区别、i与em的区别？

```plain
title与h1的区别：
定义：
    title：概括了网站信息，可以告诉搜索引擎或者用户关于这个网站的内容主题是什么
    h1：文章主题内容，告诉蜘蛛我们的网站内容最主要是什么
区别：
    title他是显示在网页标题上、h1是显示在网页内容上
    title比h1更加的重要 (title > h1 ) ==》对于seo的了解
场景：
    网站的logo都是用h1标签包裹的。
```

```plain
b与strong的区别：
定义：
    b：标签用于为文本设置粗体样式，但它只是简单地表示文本应该呈现为粗体，并不带有语义强调的意义。
    strong：标签用于表示文本的强调语义，默认会呈现为粗体，同时也向屏幕阅读器和搜索引擎表明这段文字的重要性。
区别：
    b标签只有加粗的样式，没有实际含义。
    strong表示标签内字符比较重要，用以强调的。
    
题外话：为了符合css3的规范，b尽量少用，改用strong就行了。
```

```plain
i与em的区别：
定义：
    i:标签用于表示文本的斜体样式，但它只是简单地表示文本应该呈现为斜体，并不带有语义强调的意义。
    em：标签用于表示文本的强调语义，通常会呈现为斜体，同时也向屏幕阅读器和搜索引擎表明这段文字的强调重要性。
区别：
    i只是一个倾斜标签，没有实际含义。
    em表示标签内字符重要，用以强调的。
场景：
    i更多的用在字体图标，em术语上（医药，生物）。
```

### img标签的title和alt有什么区别？

```plain
区别一：表现形式不同
    title ： 提示文本，鼠标移入到图片展示文字值
    alt   ： 替换文本，图片无法显示时展示文字值
区别二：SEO层面 ( alt > title )
    在seo的层面上，蜘蛛抓取不到图片的内容，所以前端在写img标签的时候为了增加seo效果要加入alt属性来描述这张图是什么内容或者关键词。
```

### img 标签的 srcset 的作用是什么

用于浏览器根据宽、高和像素密度来加载相应的图片资源。

```html
<img src="small.jpg " srcset="big.jpg 1440w, middle.jpg 800w, small.jpg 1x" />
```

上面的例子表示浏览器宽度达到 800px 则加载 middle.jpg ，达到 1400px 则加载 big.jpg。注意：像素密度描述只对固定宽度图片有效。

### src和href的区别

功能：

- src用于直接加载和嵌入资源。
- href用于建立导航链接，指向其他网页或资源。

上下文：

- src通常出现在脚本、图片、音频、视频等标签中。
- href通常出现在`<a>`标签和`<link>`标签中。

影响：

- 使用src时，浏览器在文档解析时会立刻发起资源请求，并暂停其他资源的加载，直到该资源加载完成。
- 使用href时，只有在用户点击链接或加载相关的`<link>`时才会触发资源请求，且不会阻止其他资源的加载解析。

### 说一说HTML的语义化

用户根据html标签名称就能够获取当前标签的意义，例如`<header> <body> <footer> <nav> <article>`。  
对于开发者而言，语义化标签有着更好的页面结构，利于个人的代码编写。  
对于用户而言，当网络卡顿时有良好的页面结构，有利于增加用户的体验。  
对于爬虫来说，有利于搜索引擎的SEO优化，利于网站更靠前的排名。  
对于团队来讲，有利于代码的开发和后续维护。

### 行内元素有哪些？块级元素有哪些？ 空(void)元素有哪些？

1. 行内元素（Inline Elements）通常是文本内容的一部分，它们不会影响布局，只占据内容所在的行宽度，宽度和高度默认由内容撑  。例如：`<span>、<a>、<img>、<b>、<strong>、<em>`等。
img标签有行内块元素的特点，但是调试工具中显示默认显示模式为inline
2. 块级元素（Block Elements）占据一行，形成独立的块，宽度默认父元素，高度默认内容撑开，可以设置宽高，影响布局。例如：
`<div>、<p>、<h1>~<h6>、<ul>、<ol>、<li>、<table>、<form>`等。
3. 空(void)元素，也称为无内容元素，它们不包含任何内容，但可以有属性。它们通常用于定义结构，不会影响布局。例子有：
`<hr>（水平线）、<br>（换行）、<img>（图片，当src为空时）、<input type="hidden">`等。  
元素之间的转换问题：  
display: inline; 把某元素转换成了行内元素 ===>不独占一行，并且不能设置宽高  
display: inline-block;把某元素转换成了行内块元素 ===>不独占一行，可以设置宽高  
display: block;把某元素转换成了块元素 ===>独占一行，并且可以设置宽高

### 怎么解决2个行内块元素中间的空白

导致原因：元素被当成行内元素排版的时候，元素之间的空白符（空格、回车换行等）都会被浏览器处理，根据white-space的处理方式（默认是normal，合并多余空白），原来HTML代码中的回车换行被转成一个空白符，所以元素之间就出现了空隙。  
方法一：手动取消空格和换行：

```html
<ul>
    <li>1</li><li>2</li><li>3</li><li>4</li>
</ul>
非常不推荐，原因：
1. 部分编译器可能会代码整理的时候会强制换行
2. 代码比较臃肿，美观度不行，一点不优雅
```

方法二：父元素设置font-size:0px（推荐）

```html
<style type="text/css">
    *{margin: 0;padding: 0;}
    ul{
        list-style: none;
        font-size: 0;
    }
    ul li{
        display: inline-block;
        width: 100px;
        height: 100px;
        background: red;
        font-size: 18px;
    }
</style>

<ul>
    <li>1</li>
    <li>2</li>
    <li>3</li>
    <li>4</li>
</ul>

注意：如果子盒子有文本，需要单独设置font-size
```

方法三：使用负 margin
通过负边距抵消空格宽度（通常 -4px，但需根据字体调整）：

```css
li {
  display: inline-block;
  margin-right: -4px;
}
```

方法四：使用 Flex 布局
将父元素设为 Flex 容器，子元素自动紧密排列：

```css
ul {
  display:flex;
}
```

方法五：浮动（Float）
改用浮动布局，但需清除浮动：

```css
li {
  float: left;
}
改用浮动布局，但需清除浮动：
```

方法六：使用 word-spacing

```css
ul {
  word-spacing: -0.25em;
}
```

推荐方案：使用 Flex 布局（方法四），简单且无副作用。  
兼容场景：若需支持旧项目，可选 font-size: 0（方法二）或 负 margin（方法三）。  
慎用方案：负 margin 和浮动需注意布局副作用。  

### 页面导入css样式时，使用link和@import有什么区别？

```plain
区别一：加载方式和顺序
    link标签会先加载（多个 <link> 标签同时引入，加载顺序由 HTML 中 <link> 标签的顺序决定）
    @import会在当前样式表加载完成后再加载引入外部样式表（@import 规则必须写在样式表的最前面，加载顺序受到 CSS 文件中 @import 规则的顺序决定。）
    加载顺序区别：页面被加载时，link 会同时被加载，而 @import 引用的 CSS 会等到页面被加载完再加载。  
区别二：权重区别
    link 方式的样式的权重高于 @import 权重。  
区别三：从属关系区别
    link 属于 HTML 标签，而 @import 是 CSS 提供的。  
区别四：兼容性区别
    link 没有兼容性问题，@import 不兼容 ie5 以下。
```

### png、jpg、gif 这些图片格式解释一下，分别什么时候用？

```plain
一、png：
    特点：png格式支持无损压缩，同样尺寸情况下，体积要比jpg/jpeg的大。
    适用场景：png格式适合保存，需要保持高质量细节和透明背景的图像，如图标、线条图、文字、Logo 等。
二、jpg：
    特点：jpg格式支持有损压缩。
    适用场景：jpg式适合保存照片、图像和艺术作品等真实场景图像，常用于网站上发布的照片、背景图等。
三、gif：
    特点：gif格式支持无损压缩和动画功能，能够保存多帧图像并以动画形式显示。
    适用场景：gif格式适合保存简单的动画、图标、表情包等图像。适用于网页上的小型动画、简单图标等。
四、webp：
    特点：webp是一种由 Google 开发的图像格式，支持有损压缩和无损压缩，通常比 PNG 和 JPG 文件大小更小，同时保持较高的图像质量。它还支持动画和透明度。
    适用场景：webp格式适合用于网站优化和速度提升，可以帮助减小图像文件大小，提高网页加载速度。特别适合用于要求高速加载和移动设备访问的网页，可以有效减少网页加载时间。
五、总结：
    PNG 适合保存高质量细节和透明背景的图像
    JPG 适合保存照片和真实场景图像；
    GIF 适合保存简单的动画和图标；
    WebP 适合用于网站优化和速度提升，特别适合要求高速加载和移动设备访问的网页（存在兼容性）。
```

### iframe的优点和缺点？

是什么：用于嵌入另一个 HTML 文档或外部资源（如网页、视频、地图等）到当前页面中。
优点：

1. 嵌入外部内容： `<iframe>` 允许你在一个网页中嵌入来自不同源或服务器的内容，这有助于创建丰富多彩的页面。
2. 独立性： 内嵌的内容在 `<iframe>` 中运行，与主页面相互隔离，这意味着它不会受到主页面的影响，保持了独立性。
3. 简便性： 使用 `<iframe>` 非常简单，只需提供要嵌入的资源的 URL 或相对路径即可。

缺点：

1. 性能问题： 如果滥用 `<iframe>`，在同一个页面中加载多个 `<iframe>` 可能会导致性能问题，因为每个 `<iframe>` 都需要单独加载资源。
2. 可访问性问题： 内嵌内容可能导致可访问性问题，因为屏幕阅读器等辅助技术可能无法正确解释和浏览 `<iframe>`内的内容。
3. 安全性风险： 如果未谨慎处理来自不受信任源的内容，可能会存在安全风险，例如点击劫持（clickjacking）攻击。

```javascript
防止自己的网站被别人 iframe 嵌套
if (top != self) {
    top.location = self.location;
}
//这段代码会检测页面是否被嵌套，如果是，则将页面重定向到自身。
```

### data-开头的元素属性是什么

`data-*`属性是HTML5新引入的自定义数据属性，

- 存储与元素相关的自定义数据。
- 方便JavaScript读取和操作。通过元素的 dataset 属性可以方便地访问 data-* 属性值，并且会自动进行驼峰式命名转换。 例如，data-user-name 可以通过 element.dataset.userName 获取值。
- 主要用于数据存储，提高代码的可读性和可维护性。

### HTML5 对比 HTML4 有哪些不同

语法和声明:在HTML5中，DOCTYPE声明变得非常简洁.
新增和废除的标签:HTML5引入了许多新的标签，使得网页开发更加简洁和语义化。例如：  

- 结构标签：`<section>、<article>、<aside>、<header>、<footer>、<nav>、<figure>`等。  
- 多媒体标签：`<video>、<audio>、<canvas>`等。
- 其他标签：`<embed>、<mark>、<progress>`等
表单控件:新增了许多input类型，如email、url、number、range、date、month、week、datetime、datetime-local、search、color、tel等。这些新类型使得表单的设计更加灵活和强大
API和功能:HTML5增加了许多新的API和功能，如Canvas绘图、SVG绘图、地理定位、拖放API、Web Worker、Web Storage、WebSocket等。这些新功能使得网页开发更加强大和灵活。

### meta标签有哪些常用用法

**元数据(metadata)元素** 的概念，用来构建HTML文档的基本结构，以及就如何处理文档向浏览器提供信息和指示，它们本身不是文档内容，但提供了关于后面文档内容的信息。
如title、base、meta都是元数据元素。

| **元素** | **meta** |
| --- | --- |
| 父元素| head |
| 属性 | http-equiv、name、content、charset |
| HTML5中的变化 | 1. charset为HTML5中新增的，用来声明字符编码;  2.http-equiv属性在HTML4中有很多值，在HTML5中只有refresh、default-style、content-type可用|

`<meta>`元素出去charset属性外，都是http-equiv属性或name属性结合content来使用

```html
<!DOCTYPE HTML>
<html>
  <head>
    <title>demo</title>
    <meta name="keywords" content="电商,物流">
    <meta name="author" content="张三">
    <meta name="description" content="网站描述...">
  </head>
  <body>
    <div>welcome</div>
  </body>
</html>
```

| 元数据名称(name的值)    | 说明                                      |
|------------------|-----------------------------------------|
| application name | 当前页所属Web应用系统的名称                         |
| keywords         | 描述网站内容的关键词,以逗号隔开，用于SEO搜索                |
| description      | 当前页的说明                                  |
| author           | 当前页的作者名                                 |
| copyright        | 版权信息                                    |
| renderer         | renderer是为双核浏览器准备的，用于指定双核浏览器默认以何种方式渲染页面 |
| viewreport       | 它提供有关视口初始大小的提示，仅供移动设备使用                 |

模拟http标头字段:  
http-equiv属性与content属性结合使用, http-equiv属性为指定所要模拟的标头字段的名称，content属性用来提供值。

```html
<meta http-equiv="参数" content="具体的描述">
```

content-Type 声明网页字符编码:

```html
<meta http-equiv="content-Type" content="text/html charset=UTF-8">
```

refresh 指定一个时间间隔(以秒为单位),在此时间过去之后从服务器重新载入当前页面,也可以另外指定一个页面.

```html
<meta http-equiv="refresh" content="2;URL=http://www.baidu.com">//2秒后在当前页跳转到百度
```

X-UA-Compatible 浏览器采取何种版本渲染当前页面

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"> //指定IE和Chrome使用最新版本渲染当前页面
```

expires 用于设定网页的到期时间，过期后网页必须到服务器上重新传输

```html
<meta http-equiv="expires" content="Sunday 22 July 2016 16:30 GMT">
```

catch-control 用于指定所有缓存机制在整个请求/响应链中必须服从的指令

```html
<meta http-equiv="cache-control" content="no-cache">//
```

content有以下值：

| content的值                            | 说明                                                                                                          |
|--------------------------------------|-------------------------------------------------------------------------------------------------------------|
| public                               | 所有内容都将被缓存(客户端和代理服务器都可缓存)                                                                                    |
| private                              | 内容只缓存到私有缓存中(仅客户端可以缓存，代理服务器不可缓存)                                                                             |
| no-cache                             | 必须先与服务器确认返回的响应是否被更改，然后才能使用该响应来满足后续对同一个网址的请求。因此，如果存在合适的验证令牌 (ETag)，no-cache 会发起往返通信来验证缓存的响应，如果资源未被更改，可以避免下载。 |
| no-store                             | 所有内容都不会被缓存到缓存或 Internet 临时文件中                                                                               |
| must-revalidation/proxy-revalidation | 如果缓存的内容失效，请求必须发送到服务器/代理以进行重新验证                                                                              |
| max-age=xxx (xxx is numeric)         | 缓存的内容将在 xxx 秒后失效, 这个选项只在HTTP 1.1可用, 并如果和Last-Modified一起使用时, 优先级较高                                           |

### 响应式图片处理优化Picture标签

它允许你放置多个 source 标签，以指定不同的图像文件名，进而根据不同的条件进行加载。

- 媒体特性结果如：视口的当前高度(viewport height)，宽度(width)，方向(orientation)。
- 像素密度：

![响应式](../img/xiangyingshi.png "响应式")

```html
<picture>
    <source srcset="smaller_landscape.jpg" media="(max-width: 40em) and (orientation: landscape)">
    <source srcset="smaller_portrait.jpg" media="(max-width: 40em) and (orientation: portrait)">
    <source srcset="default_landscape.jpg" media="(min-width: 40em) and (orientation: landscape)">
    <source srcset="default_portrait.jpg" media="(min-width: 40em) and (orientation: portrait)">
    <img srcset="default_landscape.jpg" alt="My default image">
</picture>
```

上面的代码实现了可以在一个小的景观设备上加载小的，景观裁剪图像的版本。在大的景观设备上加载大的相同的图像版本。

### 在 script 标签上使用 defer 和 async

`<script>`标签用于嵌入或引用JavaScript代码，而defer和async属性则用于改变脚本的加载和执行行为。
defer属性告诉浏览器在解析完整个页面后再执行脚本。
async属性允许脚本异步加载，这意味着浏览器可以继续解析HTML页面，同时并行下载脚本。

```html
<script type="text/javascript" defer src="example1.js"></script>
<script type="text/javascript" async src="example2.js"></script>
```

### 文档声明的作用

DOCTYPE是html5标准⽹⻚声明，且必须声明在HTML⽂档的第⼀⾏。来告知浏览器的解析器⽤什么⽂档标准解析这个 ⽂档，不同的渲染模式会影响到浏览器对于 CSS 代码甚⾄ JavaScript 脚本的解析。
⽂档解析类型有：
BackCompat：怪异模式，浏览器使⽤⾃⼰的怪异模式解析渲染⻚⾯。（如果没有声明DOCTYPE，默认就是这个模式）
CSS1Compat：标准模式，浏览器使⽤W3C的标准解析渲染⻚⾯

### SVG和Canvas的区别

- svg是矢量图，canvas是位图，svg不依赖分辨率，canvas依赖分辨率，svg放大缩小不会失真，canvas会失真。
- svg使用XML来描述图形，canvas使用像素来绘制图形，svg可以制作复杂的图形，canvas更适合制作简单的2D图形。
- svg支持分层和事件，canvas不支持，svg中的文字可保留，可编辑和可搜索，canvas的文本渲染能力弱。
- svg节点过多时渲染慢，canvas性能更好，但写起来更复杂，svg适合大型渲染区域的应用，canvas适合图形密集型游戏。

### 谈谈WebWorker

[聊一下对 WebWorker 的理解](http://juejin.cn/post/7350181789531619379)。
WebWorker是一种在 Web 应用中实现`多线程运行`的技术，可以将耗费 CPU 的任务交给`后台线程处理`，`避免阻塞主线程`，从而提高 Web 应用的响应性能和用户体验。 总之，WebWorker的引入解决了 Web 应用长期以来在`单个线程`中运行所带来的诸多问题，有效提升了Web应用的运行性能和用户体验。

### 浏览器内核

浏览器内核是浏览器的核心组件，主要负责解析和渲染网页内容。常见的浏览器内核包括：

- Trident：IE浏览器的内核。
- Blink：Chrome浏览器的内核，之前是Webkit内核。
- Gecko：Firefox浏览器的内核。
- Webkit：Safari浏览器的内核。
不同的浏览器内核在网页的语法解释和渲染方式上可能存在差异，因此开发者需要在不同内核的浏览器中测试网页的显示效果，以确保网页的兼容性和用户体验。

### 前端如何做好SEO

[前端进阶：SEO 全方位解决方案](https://juejin.cn/post/7241813423460581435)。

1. TDK优化
2. 网站质量
3. SEO手段（10种手段）
一、TDK是Title(页面标题)、Meta Description（页面描述）和Meta Keywords（页面关键词）的缩写，对网站的这三个信息的提炼是网站SEO的重要环节。
但是由于一些原因，各大主流搜索引擎基本都已经大大降低甚至移除了 `<keywords>` 对排名的影响。
title标签相当于网站的名片，他会直接显示在搜索结果中。一个好的标题势必可以为网站带来流量，从而提升网站排名。注意：网站标题避免冗长。

```html
例如：<title>掘金</title>
```

META标签是网页head区的辅助性标签，它的作用是经过配置一些参数用以描述页面属性。目前几乎所有搜索引擎都使用网上机器人自动查找meta值来给网页分类。
meta标签的属性有两种：name和http-equiv。
"name"属性有以下配置项：

- Keywords(关键词，现在不再重要了)：逗号分隔的关键词列表（告诉搜索引擎页面是与什么相关的）；
- description(网站内容描述，很重要)：页面描述。搜索引擎会把这个描述显示在搜索结果中；
- format-detection：格式检测，比如禁止识别电话，邮箱等；
- author：作者的名字；
- Robots：用来告诉搜索机器人哪些页面需要索引，哪些页面不需要索引；
- theme-color：网站主题色；

```html
<meta name="keywords" content="掘金,稀土,Vue.js,前端面试题,Kotlin,ReactNative,Python">

<meta name="description" content="掘金是面向全球中文开发者的技术内容分享与交流平台。我们通过技术文章、沸点、课程、直播等产品和服务，打造一个激发开发者创作灵感，激励开发者沉淀分享，陪伴开发者成长的综合类技术社区。">

<meta name="format-detection" content="telephone=no">

<meta name="author" content="cece">

<Meta name="Robots" Content="Nofollow">
/** 
all：文件将被检索，且页面上的链接可以被查询；  
none：文件将不被检索，且页面上的链接不可以被查询；(和 "noindex, no follow" 起相同作用)  
index：文件将被检索；（让robot/spider登录）  
follow：页面上的链接可以被查询；  
noindex：文件将不被检索，但页面上的链接可以被查询；(不让robot/spider登录)  
nofollow：文件将不被检索，页面上的链接可以被查询。(不让robot/spider顺着此页的连接往下探找)
*/

<meta name="theme-color" content="#4285f4" />
```

"http- equiv"属性有以下配置项：
http-equiv顾名思义，相当于http的文件头作用，它可以向浏览器传回一些有用的信息，以帮助正确和精确地显示网页内容。

```html
<meta http-equiv="参数"content="参数变量值">；
```

- refresh(期限)：定义文档自动刷新的时间间隔（下面content中的2是指停留2秒钟后自动刷新到URL网址）。这个属性值慎重使用，因为它会使得页面不受用户控制；
- set-cookie：如果网页过期，那么存盘的cookie将被删除；

```html
<meta http-equiv="refresh" content="2;URL=http://www.baidu.com">

<meta http-equiv="Set-Cookie"content="cookie value=xxx;expires=Friday,12-Jan-200118:18:18GMT；path=/">
```

二、网站质量：
网站性能是会影响到网站的SEO排名的，原因可想而知：

- 网站卡顿势必会大大降低网站的用户留存率；
- 如果网站加载缓慢，搜索引擎就会认为该网站对用户不友好，从而将其排名下降；
- 影响搜索引擎蜘蛛的爬取频率；
HTML语义化：语义化是指内容的结构化（内容语义化），选择合适的标签（代码语义化）。
杜绝通篇div，HTML语义化不仅便于开发者阅读，还有利于浏览器爬虫的解析，对seo优化很有帮助。
所以我们在开发时要遵循语义化的开发规范，根据页面内容，选择合适的标签，优化代码，使得网页结构更加清晰。
- SEO的禁忌之一就是用JS输出重要的内容。爬虫不会读取JS格式的内容，所以重要的内容必须是HTML格式，这也就是为什么现在流行的spa框架都不利于seo的原因之一；
- 尽量不使用iFrame。因为搜索引擎不会抓取iframe内的内容，所以重要内容绝对不能放在iframe中；
- 如果需要截取文字，尽量用css实现，保证文字可以完整呈现给搜索引擎。
