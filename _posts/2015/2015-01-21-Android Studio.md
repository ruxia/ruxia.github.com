---
layout: post
title: Android Studio的安装配置
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
>- 插件配置

---

##Android Studio简介

###Android Studio的推出
2013年5月16日，在I/O大会上，谷歌推出新的Android开发环境——Android Studio，并对开发者控制台进行了改进。首先解决的一个问题是**多分辨率**，开发者可以在编写程序的同时看到自己的应用在不同尺寸屏幕中的样子。而且，增加了**五个新的功能**，包括优化小贴士、应用翻译服务、推荐跟踪、营收曲线图、用版测试和阶段性展示。而且给出一些工程模板，比如Google Maps Activity，login Activity等，非常方便。个人而言，Android Studio的出现确实给Android开发者们提供了**更加友好的开发环境**。

###下载
Android Studio更新速度比较快（可见下图），目前最新版本为v1.0.1，所以需要时可自行到官网下载 [Android Studio官网](https://developer.android.com/sdk/installing/studio.html#download "https://developer.android.com/sdk/installing/studio.html#download") 。  
![](/image/version.png)

##Android Studio安装
###JDK的安装
关于JDK的安装没什么需要特殊注意的，最容易出现错误的就是配置环境变量的过程。本人由于当时少了一个\，纠结了很久找不出问题，如此简单的过程这样实在是费时费心。所以这里给出精确的环境变量配置，望给大家的配置过程提供一些便利。  
共有三个环境变量需要配置，首先，找到“**计算机→属性→高级系统设置→高级→环境变量→系统变量**”，然后进行下面三步：  
> 1. *JAVA_HOME*→*`D:\Program Files\Java\jdk1.8.0_25\`\*   
> 新建*JAVA_HOME*变量，变量值填写jdk的安装目录，比如 *D:\Program Files\Java\jdk1.8.0_25\\*。（我当时就是忽视了最后的\导致的问题）
> 
> 2. *Path*→*%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;*    
> 找到*Path*变量，编辑，在变量值最后输入 *%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;*（注意原来Path的变量值末尾有没有分号，如果没有，先输入分号再输入上面的代码）   
> ![](/image/path.png) 
> 
> 3. *CLASSPATH*→*.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar*    
> 新建*CLASSPATH*变量，变量值填写 *.;%JAVA_HOME%\lib;%JAVA_HOME%\lib\tools.jar*     
![](/image/classpath.png)  

检查是否配置成功，运行cmd，输入java -version，如下图所示，则配置成功。  
![](/image/test.png)

##配置

###字体颜色配置

1. 更改主题。默认的Android Studio为灰色界面，感觉黑色的Darcula主题很炫酷。Settings --> Appearance --> Theme，选择Darcula主题即可。系统字体中文显示可改为这样，Settings --> Appearance，勾选 Override default fonts by (not recommended)，微软雅黑效果不错。  
![](/image/theme.png)

2. 更改编程字体。Settings --> Editor --> Colors & Fonts --> Font。最漂亮的编程字体当属Consolas，15。由于系统默认的是不能编辑的，所以若要更改，则需要保存一份自己的设置，点击右侧的Save As，保存自己的设置，在Editor Font中即可设置字体。勾选Show only monospaced fonts，表示只显示等宽字体，因为编程等宽字体使用效果较好。  
![](/image/editfont.png)

###快捷键、便捷功能配置

1. 快捷键设置及更改。Settings --> Keymap。个人觉得一般不用更变。  
![](/image/keymap.png)

2. 显示行号。Settings --> Editor --> Appearance，勾选Show line numbers。  
![](/image/linenum.png)

3. 显示空格。有利于规范格式。Settings --> Editor --> Appearance，勾选Show whitespaces。  
![](/image/whitespace.png)

4. 自动导入所需引用。当从其他地方复制一段代码到Android Studio中，默认的Android Studio不会自动导入这段代码中使用到的类的引用，所以可设置如下。Settings --> Editor --> Auto Import，勾选Add unambiguous improts on the fly。  
![](/image/autoimport.png)

###插件配置

1. 插件禁用。Settings --> Plugins，显示已默认安装的插件列表，取消勾选即可禁用插件。我禁用的插件：
> CVS Integration（CVS 版本控制系统）  
> Google Cloud Tools For Android Studio（Google云）  
> Google Login（Google账号登录）  
> hg4idea（Mercurial版本控制系统）

![](/image/plugins.png)  
注意：如果禁用了上图列表2和3选项，将导致不能使用导入官方样例的功能（import sample）。

2. 插件安装。Settings --> Plugins --> Browse repositories，搜索安装。比如我安装的Git版本控制插件.gitignore support，如上图。   
注意：如果使用Git进行版本控制，需要设置Git的安装文件目录。Settings --> Version Control --> Git，在右侧中选择Git的安装目录。  
![](/image/versioncontrol.png)

------


> 以上是我第一次安装设置Android Studio过程中的一些经验和技巧，希望可以帮助新手们更快的上手，也欢迎大家补充。