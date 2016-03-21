---
author: xjh1994
comments: true
date: 2013-06-08 06:54:38+00:00
layout: post
slug: install-curl-extension-on-linux-or-windws
title: 安装Curl的方法:(Linux/Windows)
wordpress_id: 259
categories:
- Linux
- Mac
- PHP&amp;MySQL
- Windows
tags:
- Apache
- Curl
- Linux
- Nginx
- PHP
- Ubuntu
- Windows
- Windows 8 Metro
- windows7
---

[caption id="" align="alignnone" width="444"]![curl](http://www.putaojiayuan.com/uploadfile/2011/0316/20110316101909952.jpg) curl[/caption]

Curl是利用URL语法在命令行方式下工作的文件传输工具，支持很多协议，如HTTP、FTP、TELNET等。在PHP等语言开发的实例中经常使用的到。那么在Lamp服务器上如何安装呢？



* * *




通用Linux下：




--获得安装包，从网上直接下载或者其他途径，这里直接wget
# wget http://curl.haxx.se/download/curl-7.17.1.tar.gz
--解压到当前目录
# tar -zxf curl-7.17.1.tar.gz
--进入解压后的目录内
# cd curl-7.17.1
--配置，指定安装的目录，这里是“/usr/local/curl”
# ./configure --prefix=/usr/local/curl
--
# make
--安装
# make install
--安装完毕


使用：
将curl命令加入环境变量，
命令行里执行（仅对本会话起作用，或者在.bash_profile、.bashrc文件里配置环境变量）：
# export PATH=$PATH:/usr/local/curl/bin

然后就可以使用了



* * *



Ubuntu下，只需一条命令即可：


<blockquote> sudo apt-get install curl libcurl3 libcurl3-dev php5-curl</blockquote>


然后重新启动你的服务器：


<blockquote>sudo /etc/init.d/apache2 restart</blockquote>


此时Curl就已经安装完毕了，你可通过包括：<?php phpinfo(); ?>内容的PHP文件来查看安装是否成功了。



* * *



Windows系统下curl扩展开启的步骤：

1、将PHP文件夹下的三个文件php_curl.dll,libeay32.dll,ssleay32.dll复制到system32下;

2、将php.ini(c:WINDOWS目录下)中的;extension=php_curl.dll中的分号去掉;

3、重启apache或者IIS。
