---
layout: post
title: Responsible Design响应式设计
summary: 简而言之，一个网站能够兼容多个终端。包括响应式布局和响应式内容，这里主要讲的是响应式布局。
categories:
- design
tags:
- Responsible Design
- design
---

很久很久很久以前，每个人都只有一件衣服（*Website*），不管有钱没钱大家每天都只穿这一件。
后来有人发明了舞会（*移动互联网*），大家都争先恐后地想要参加，于是一个裁缝甲「*开发*」忽悠人们说进舞会最好订做一件专门的礼服（*Mobile Site*），大家想想也对，上班和出去哈皮都穿同一件衣服多无聊啊，舞会就要有舞会的样子。于是乎只要有点闲钱的人都做了礼服，他和原来那件衣服是完全不一样的，面子不一样，里子也不一样。
后来舞会的种类越来越多了，很多人被迫做了好多好多件礼服，于是又有一个裁缝乙「*前端*」站出来说你们每年要新做那么多衣服，多费钱啊，而且一出门钥匙啊钱包啊名片都要在不同衣服里换来换去多麻烦。你看，我们新发明了一个手艺「***Responsive Design***」，只要把你原来那件衣服稍微那么一改，以后去哪个舞会都可以只穿这一件衣服，衣服的里子永远都差不多，但面子可以按照要求自适应不同的舞会。
于是所有人都开始换上这种响应式的衣服了。

##Responsible Design的提出者
---
![](/image/ethan.jpg)

Ethan Marcotte（伊桑·马科特）于2010年5月提出Responsible Design的理念。尤其是2013年，响应式设计被大量应用到博客等各网站中，风靡一时。


- Ethan Marcotte是一个多才多艺的用户体验设计师和开发者。
- 曾为纽约杂志(New York Magazine)、哈佛大学以及世界互联网组织W3C等客户服务。
- 后加入Happy Cog—是为企业家服务的高度优化的网站托管供应商，专门为高端拥有巨大流量的网站效力。
- 参与编辑Bulletproof Web Design，Designing With Web Standards
##Responsible Design
---

响应式设计，简单来说，就是一个网站能够兼容多个终端。主要包括响应式布局和响应式内容，这里主要讲的是响应式布局。响应式布局就像下图中所示，在不同大小的屏幕上，网页自适应的显示不同的布局。

![](/image/responsible.jpg)

- CSS media query 技术
- 用Javascript来操作HTML内容
- 在服务器端操作HTML内容

##Media query
---

###Media type
css2有Media type，特性如下：

- Media类型：aural（声音），braille（触摸），print（打印），handheld（移动设备），embossed，projection，screen，speech，tty，tv。
- @media规则可以在同一样式表里为不同终端使用不同的样式
由于Media type当时并不被多数移动终端支持，所以没有被广泛使用。

###Media query
css3有了Media query，Media query已经被大多数移动终端支持。

- 表达式：
	`@media 媒体类型 关键字 (设备特性) {样式代码}`
- 关键字：and，not，only
- 设备特性：min-width, min-height等

当然Media query依然有Media type的10中媒体类型，通过指定相应的媒体类型和设备特性，media query 技术会自动跟你设置的css进行匹配。

###Media query在网页中的位置

1. 在link中使用@media：

`<link rel="stylesheet" type="text/css" media="only screen and (max-width: 480px), only screen and (max-device-width: 480px)" href="link.css"/>`

2. 在样式表中内嵌@media：

`@media (min-device-width:1024px) and (max-width:989px), screen and (max-device-width:480px),(max-device-width:480px) and (orientation: landscape), (min-device-width:480px) and (max-device-width:1024px) and (orientation:portrait) {srules}`

###Media query写法
---
`@media screen and (min-width: 320px) and (max-width : 479px)`

这是Media query最简单的一句代码，大家应该都能看出来，这是屏幕在320px到479px时要显示的部分。

`@media screen and (max-width : 320px){
body{...}
}`

`@media screen and (min-width: 800px) and (max-width: 1024px){
body{...}
}`

此处有一个特殊情况，对于高像素比的终端，比如iPhone4以上的retina屏幕。

这里普及两个小知识：
- 像素比：指的是图像中的一个像素的宽度与高度之比。比如640×480的像素比1.0，720×480的像素比0.9。
- retina屏幕：分辨率超高的屏幕。如iPhone4、iPhone4s：3.5寸 960x640，iPhone5：4寸 1136x640。可见iPhone的像素比是超高的，所以已经不能保证一般的图片在该终端上依然显示清晰，必须进行特殊的处理。

为了适配高像素比终端，就要加上下面这段代码：

`@media only screen and (**-moz-min-device-pixel-ratio: 2**), only screen and (-o-min-device-pixel-ratio: 2/1), only screen and (-webkit-min-device-pixel-ratio: 2), only screen and (min-device-pixel-ratio: 2){
body{
font-size:24px;
}
.box2{
background: url(d/20.png) #ccc;
**background-size:50%**;
}}`

通过以上代码，使得1px的图片，首先做成2px的图片，再缩放到50%，显示为1px，这样便可清晰地显示在高像素比的终端上。

##响应式设计的优缺点

优点：
- 面对不同分辨率设备灵活性强；
- 能够快捷解决多设备显示适应问题。
缺点：
- 兼容各种设备工作量大，效率低下；
- 代码累赘，会出现隐藏无用的元素，加载时间加长；
- 一定程度上改变了网站原有的布局结构，会出现用户混淆的情况。

##相关链接

- [http://www.bootcss.com/](http://www.bootcss.com/)
- [http://www.bootcss.com/p/google-bootstrap/index.html](http://www.bootcss.com/p/google-bootstrap/index.html)
- [http://www.jiawin.com/](http://www.jiawin.com/)
- [http://www.daqianduan.com/25-responsive-design/](http://www.daqianduan.com/25-responsive-design/)
- [http://www.caihong.cc/?p=250](http://www.caihong.cc/?p=250)