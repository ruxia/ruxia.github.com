---
layout: post
title: Android Studio的配置
categories:
- Android
tags:
- Android Studio
- design
---


>###Android Studio的安装和配置

>- 安装
>- 字体、颜色配置
>- 快捷键、便捷功能配置
>- 大众偏好配置

---

##Android Studio简介

###Android Studio的推出
2013年5月16日，在I/O大会上，谷歌推出新的Android开发环境——Android Studio，并对开发者控制台进行了改进。首先解决的一个问题是**多分辨率**，开发者可以在编写程序的同时看到自己的应用在不同尺寸屏幕中的样子。而且，增加了**五个新的功能**，包括优化小贴士、应用翻译服务、推荐跟踪、营收曲线图、用版测试和阶段性展示。个人而言，Android Studio的出现确实给Android开发者们提供了**更加友好的开发环境**。

###下载
Android Studio更新速度比较快（可见下图），目前最新版本为v1.0.1，所以需要时可自行到官网下载 [Android Studio官网](https://developer.android.com/sdk/installing/studio.html#download "https://developer.android.com/sdk/installing/studio.html#download") 。  
![](/image/version.png)

##Android Studio安装
###JDK的安装
关于JDK的安装没什么需要特殊注意的，最容易出现错误的就是配置环境变量的过程。本人由于当时少了一个\，纠结了很久找不出问题，如此简单的过程这样实在是费时费心。所以这里给出精确的环境变量配置，望给大家的配置过程提供一些便利。  
共有三个环境变量需要配置，首先，找到“计算机→属性→高级系统设置→高级→环境变量→系统变量”，然后进行下面三步：  
> 1. *JAVA_HOME*，*D:\Program Files\Java\jdk1.8.0_25\\*   
> 新建*JAVA_HOME*变量，变量值填写jdk的安装目录，比如 *D:\Program Files\Java\jdk1.8.0_25\\*。（我当时就是忽视了最后的\导致的问题）
> 2. *Path*，*%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;*    
> 找到*Path*变量，编辑，在变量值最后输入 *%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;*（注意原来Path的变量值末尾有没有分号，如果没有，先输入分号再输入上面的代码）   
> ![](/image/path.png) 
> 3. *CLASSPATH*，*.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar*    
> 新建*CLASSPATH*变量，变量值填写 *.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar*     
![](/image/classpath.png)  
检查是否配置成功，运行cmd，输入java -version，如下图所示，则配置成功。  
![](/image/test.png)

##配置

###字体颜色配置

![](/image/axure.jpg)

1. 命令区。和操作所有office软件一样，包含文件、编辑、查看和帮助，这些功能差不多。而Axure特有的几个特殊的命令栏目是线框图（wireframe），包含所有画原型线框图的相关命令；对象（object），包含所有对工作区物体的操作命令，操作放入工作区的所有widgets，包括组合、排序、锁定以及脚注命令等；生成（generate），自动生成html演示文件、word说明文档，以及对生成规则进行自行编辑、定义。
2. 工具栏。基本和office风格一模一样，功能也很容易上手。
3. 工作区。这就是平时操作创建prototype的空间，想法实现的地方。
4. 站点地图。Axure创建的文件是模拟真实网站页面关系的，sitemap就是通过树形目录关系，管理所有的站点页面文件与流程图文件。科学的文件关系结构，对有效的演示文档与生成易读的说明文档相当重要。
5. 器具箱。这里有所有用来画wireframe与流程图的对象。我们可以通过拖拽的方式将小图形放入工作区，进行操作。对于这里面的对象，我们有必要一一详细了解。
6. 复用模块区。这里创建的页面文件和sitemap的页面相似，唯一不同的是，master的每个文件，可以当作一个整体，被sitemap反复调用。这个功能就相当于程序开发中的程序复用，用好这个功能，可以减少我们很大一部的工作量。也更容易理解网页文件的关系，了解网页设计师、程序员是怎么构建网站的页面的。
7. 页面笔记与交互区。这个注释和交互和8不同，7针对的是页面，用来对当前创作页面进行注释与说明，同时可以在这里对页面里的关键字段和特殊问题进行详细的描述。
8. 控件注释与交互区。这里针对的是页面中的元素，也就是一个个widgets。

###控件的交互
控件交互面板用于定义线框图中控件的行为，包含定义简单的链接和复杂的RIA（Rich Internet applications）行为，所定义的交互都可以在将来生成的原型中进行操作执行。
在控件交互面板中可以定义控件的交互，交互事件（Events）、场景（Cases）和动作（Actions）组成：

- 用户操作界面时就会触发事件，如鼠标的 OnClick、OnMouseEnter和OnMouseOut；
- 每个事件可以包含多个场景，场景也就是事件触发后要满足的条件；
- 每个场景可执行多个动作，例如：打开链接、显示面板、隐藏面板、移动面板。

##学习途径

- 打开软件，按F1调取帮助文档，对照文档学习。
- [http://www.axure.com/au-home.aspx](http://www.axure.com/au-home.aspx) 视频学习。
- Axure博客[http://axure.com/cs/blogs/Default.aspx](http://axure.com/cs/blogs/Default.aspx)。
- 讨论组[http://axure.com/cs/forums/Default.aspx](http://axure.com/cs/forums/Default.aspx)。

##汉化方法

PC windows，将汉化文件解压后放在新建的lang文件夹中，然后将lang文件夹放到Axure安装文件的根目录下即可。
![](/image/hanhua.png)