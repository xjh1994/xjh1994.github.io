---
author: xjh1994
comments: true
date: 2013-06-08 05:42:20+00:00
layout: post
slug: inux-svn-rabbitvcs
title: 媲美TortoiseSVN的LINUX版SVN客户端软件RabbitVCS
wordpress_id: 256
categories:
- Linux
- Mac
- PHP&amp;MySQL
- 开源项目
- 操作系统
- 系统工具
- 软件应用
tags:
- Linux
- PHP
- RabbitVCS
- SVN
---

[caption id="" align="alignnone" width="827"]![RabbitVCS](http://www.48474.com/wp-content/uploads/2010/09/context_menu.png) RabbitVCS[/caption]

如果想在Linux环境下使用图形化界面的SVN客户端软件，那么RabbitVCS绝对是首选，可以媲美Windows环境下用的TortoiseSVN，甚至连操作都基本一样，所以强烈推荐给各位童鞋。
RabbitVCS基本支持所有的Linux发行版本包括Ubuntu、Debian、Fedora、Arch Linux、Gentoo、Mandriva、OpenSUSE、RHEL、CentOS 5等。其官网地址为http://www.rabbitvcs.org/
**在ubuntu下安装**
首先添加源：


sudo add-apt-repository ppa:rabbitvcs/ppa
sudo vi /etc/apt/sources.list


按SHIFT + g 跳转到尾行 按 o 回车输入


deb http://ppa.launchpad.net/rabbitvcs/ppa/ubuntu karmic main


按ESC后按SHIFT + z + z 保存并退出
下面是导入key并安装


sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 34EF4A35
sudo apt-get update
sudo apt-get install rabbitvcs-cli rabbitvcs-core rabbitvcs-gedit rabbitvcs-nautilus rabbitvcs-thunar thunarx-python


**在Fedora12或更高版本**


yum install rabbitvcs*


**在Arch Linux中**


yaourt -S python-nautilus python-configobj pygtk pysvn dbus-python subversion meld rabbitvcs


**在Gentoo中**


emerge rabbitvcs


安装完毕后，注销一下，重新登录，在文件夹和文件夹内点击鼠标右键就用RabbitVCS操作工具了。

[rabbitvcs-0.13.3-1.el5.i386.rpm](http://orannis.hmdc.harvard.edu/rpmforge/rabbitvcs/rabbitvcs-0.13.3-1.el5.i386.rpm)

[http://orannis.hmdc.harvard.edu/rpmforge/rabbitvcs/](http://orannis.hmdc.harvard.edu/rpmforge/rabbitvcs/)

转自[http://zhumeng8337797.blog.163.com/blog/static/100768914201152174958234/](http://zhumeng8337797.blog.163.com/blog/static/100768914201152174958234/)
