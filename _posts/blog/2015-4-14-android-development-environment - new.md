---
layout: post
title: Android开发环境搭建-NEW
description: 使用Eclipse来做android开发的另一种方式是使用独立的SDK，然后给Eclipse添加ADT插件。所以这次使用下载installer_r24.1.2-windows.exe的方式来搭建环境。
category: blog
---

现在[android开发官网][2]主推Android Studio来开发android应用程序，但是之前广泛使用的是Eclipse，所以还是使用Eclipse来搭建环境吧。

## JAVA环境 ##
开发android应用需要Java开发环境，所以需要[下载JDK][3]安装，这里选择了使用Java 7，寻找jdk-7u71-windows-x64.exe（64位Windows系统）或jdk-7u71-windows-i586.exe（32位Windows系统）安装，然后设置环境变量。

计算机-->属性-->高级系统设置-->环境变量

1. 新建系统变量：变量名为 JAVA_HOME，变量值为Java的安装目录，我这里为 C:\Program Files\Java\jdk1.7.0_71
2. 在系统变量中寻找PATH变量并编辑，在其值后添加%JAVA_HOME%\bin;注意各个值之间使用英文下的;隔开
3. 新建系统变量：变量名为 CLASSPATH，变量值为 %JAVA_HOME%\lib\tools.jar;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib

配置完毕之后，通过cmd运行命令：java -version，出现以下画面，则说明安装成功。

![Java version](/images/android-env/javaenv.jpg)


## android环境 ##
在[android开发官网][2]下载android SDK，这里选择推荐的Windows平台的installer_r24.1.2-windows.exe，官网需要翻墙。下载后，直接运行安装程序安装，在安装过程中更改了安装目录，我这里为E:\androiddevelop；安装完成后的目录结构为下图所示：

![android dir](/images/android-env/androiddir.jpg)


然后设置环境变量，在系统变量中新建变量，变量名为ANDROID_SDK_HOME，变量值为刚才解压缩的文件夹中的sdk位置，即是E:\androiddevelop

然后在系统变量path变量中添加值 %ANDROID_SDK_HOME%\tools;%ANDROID_SDK_HOME%\platform-tools

这里说明一下ANDROID_SDK_HOME系统变量的作用，在创建管理AVD的时候，开发者创建的虚拟设备保存在%ANDROID_SDK_HOME%\.android路径下，如果不设置则默认保存在C盘的系统用户中，可能会占用较大的空间。


## android SDK ##

未完待续

## 可能出现的问题 ##
由于我们是中国特色主义和谐社会，所以机器人这么暴力的东西还是抵御在长城的外围比较好，但是我们这群人可就遭殃了，还让不让人好好的玩机器人了，这就是出现的问题，看下图。

![Eclipse](/images/android-env/problem.jpg)

我要下载android开发的工具，但是竟然不能访问http://dl-ssl.google.com网站，导致无法下载。谢谢和谐社会。

解决方法请参考上一篇文章。



[BeiYuu]:    http://beiyuu.com  "BeiYuu"
[1]:    {{ page.url}}  ({{ page.title }})
[2]: http://developer.android.com/
[3]: http://www.oracle.com/technetwork/java/javase/downloads/index.html