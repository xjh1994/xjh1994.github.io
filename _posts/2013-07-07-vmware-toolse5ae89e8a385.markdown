---
author: xjh1994
comments: true
date: 2013-07-07 02:36:25+00:00
layout: post
slug: vmware-tools%e5%ae%89%e8%a3%85
title: VMware Tools安装
wordpress_id: 474
categories:
- 未分类
---

**注意：VMware Tools是在某个虚拟机启动后在其系统中安装的，并非是在自己的系统中安装。**

把VMwareWorkstation虚拟机装好了，准备测试软件的时候，发现不能复制，粘贴，根据已有的经验，是VMwareTools没有安装好，于是乎，又把VMareTools安装了。

首先下载VMware Tools的镜像：[windows.iso](ftp://jb51user:www.jb51.net@xl.jb51.net:8021/201205/tools/VMware8_jb51.rar)

下载好后解压到任意位置，设置你要安装的虚拟机CD-ROM，加载之前解压得到的文件，启动虚拟机。
下面是图文安装顺序和安装界面：
1、打开虚拟机的我的电脑

![VMware Tools安装图文教程 三联教程](http://files.jb51.net/file_images/article/201205/20120530101113133.jpg)　　2、打开可移动存储的设备(VMwareTools)

![](http://files.jb51.net/file_images/article/201205/20120530101113134.jpg)　　3、运行"setup.exe"，就到了VMwareTools的安装向导界面

![](http://files.jb51.net/file_images/article/201205/20120530101113135.jpg)　　4、典型安装

![](http://files.jb51.net/file_images/article/201205/20120530101113136.jpg)　　5、点击安装：

![](http://files.jb51.net/file_images/article/201205/20120530101113137.jpg)　　6、安装向导完成，OK了。

![](http://files.jb51.net/file_images/article/201205/20120530101113138.jpg)　　PS：安装完后需要重启虚拟机系统，之后就可以跟宿主机进行复制粘贴等操作了。
如果没有VMareTools文件，可以到这里
[下载VMwareTools8.8.0中文版：VMwareTools8.8.0中文版](http://www.jb51.net/softs/45337.html)



部分转自[http://www.jb51.net/os/windows/WinXP/45334.html](http://www.jb51.net/os/windows/WinXP/45334.html)
