---
author: xjh1994
comments: true
date: 2013-06-08 04:10:00+00:00
layout: post
slug: '%e3%80%90nginx%e3%80%91linux%e4%b8%8bapache-%e8%bd%ac%e7%94%a8-nginx%ef%bc%88php5mysqlphpmyadminfastcgi%ef%bc%89-3'
title: 【Nginx】Linux下Apache 转用 nginx（php5+mysql+phpmyadmin+FastCGI）
wordpress_id: 469
categories:
- 未分类
---

<blockquote>ubuntu</blockquote>




![Nginx](http://a0.att.hudong.com/16/95/19300001392982131934951779953.png)Nginx




看到Nginx的速度，相信好多朋友都想从Apache转向Nginx了，我也不例外。今天就在ubuntu下面尝试了一下Nginx的安装和配置。这里将安装配置过程中遇到的问题分享给大家，希望对大家有所帮助。（部分教程转载于网上资料）



* * *



**Nginx**（发音同 engine x）是一款轻量级的Web 服务器/反向代理服务器及电子邮件（IMAP/POP3）代理服务器，并在一个BSD-like 协议下发行。由俄罗斯的程序设计师Igor Sysoev所开发，供俄国大型的入口网站及搜索引擎Rambler（俄文：Рамблер）使用。其特点是占有内存少，并发能力强，事实上nginx的并发能力确实在同类型的网页服务器中表现较好.它以占用系统资源少，运行效率而成为web服务器的后起之秀。中国大陆使用nginx网站用户有：新浪、网易、 腾讯等大型信息网站，还有淘宝网站使用的是nginx二次开发的web服务器。



* * *



前期工作：

1、停止Apache 。 sudo /etc/init.d stop

2、正常情况下大家的php5 mysql phpmyadmin等都是安装好了的，如果没有装好的朋友可以看下下面的教程。

1. 使用官方[PPA](http://imcn.me/html/y2011/3695.html)安装 Nginx 最新版本，使用以下命令：

sudo add-apt-repository ppa:nginx/stable
sudo apt-get update
sudo apt-get install nginx

Nginx相关控制命令：


<blockquote>将nginx加入开机启动

_update-rc.d nginx defaults_
启动 Nginx：
sudo /etc/init.d/nginx start
浏览器浏览运行情况输入：http://localhost ;</blockquote>


如果出现”Welcome to nginx!”，表明你的 Nginx 服务器安装成功！

关闭 Nginx：sudo /etc/init.d/nginx stop;
重启 Nginx：sudo /etc/init.d/nginx restart;



* * *



2. 安装 PHP，输入以下命令：

_sudo apt-get install php5-cli php5-cgi php5-fpm php5-mcrypt php5-mysql_

_配置Nginx站点，设置：_

___sudo vi /etc/nginx/sites-available/default_

_修改 “index” 为：“index index.php index.htm index.html;“_
`
`



**[...]**

**server {**

**        listen   80;**

**        server_name  _;**

****

**        access_log  /var/log/nginx/localhost.access.log;**

** **

****

**        location / {**

**                root   /var/www/;**

**                index  index.php index.html index.htm;**

**        }**

** **

**        location /doc {**

**                root   /usr/share;**

**                autoindex on;**

**                allow 127.0.0.1;**

**                deny all;**

**        }**

** **

**        location /images {**

**                root   /usr/share;**

**                autoindex on;**

**        }**

** **

**        #error_page  404  /404.html;**

** **

**        # redirect server error pages to the static page /50x.html**

**        #**

**        error_page   500 502 503 504  /50x.html;**

**        location = /50x.html {**

**                root   /var/www/;**

**        }**

** **

**        # proxy the PHP scripts to Apache listening on 127.0.0.1:80**

**        #**

**        #location ~ .php$ {**

**                #proxy_pass   http://127.0.0.1;**

**        #}**

** **

**        # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000**

**        #**

**        location ~ .php$ {**

**                fastcgi_pass   127.0.0.1:9000;**

**                fastcgi_index  index.php;**

**                fastcgi_param  SCRIPT_FILENAME  /var/www/nginx-default$fastcgi_script_name;**

**                include        /etc/nginx/fastcgi_params;**

**        }**

** **

**        # deny access to .htaccess files, if Apache’s document root**

**        # concurs with nginx’s one**

**        #**

**        location ~ /.ht {**

**                deny  all;**

**        }**

**}**

**[...]**



可以直接复制过去，以免修改过程中出现错误。
测试，创建网站目录
sudo mkdir /var/www/
建立一个虚拟站点：
sudo vi /etc/nginx/sites-available/default
修改root目录: “root /var/www;”
建立一个测试页面：
sudo vi /var/www/index.php
在测试页面index.php中加入以下代码:

<?php phpinfo();?>

重启nginx

sudo /etc/init.d/nginx restart

_浏览器输入以下地址，看看有没有安装成功！_

http://localhost/index.php

3、安装FastCGI

[Ubuntu](http://www.linuxidc.com/topicnews.aspx?tid=2)没有独立的FastCGI安装包，所以用lighttpd里面的spawn-fcgi,运行下面命令:

_apt-get install lighttpd_

安装完成时会出现lighttpd无法启动的错误，因为nginx占用了80端口。运行

_update-rc.d -f lighttpd remove_

使lighttpd开机不启动。

我们安装lighttpd只需要其中的_/usr/bin/spawn-fcgi__，_来运行FastCGI进程。运行

_spawn-fcgi –help_

查看它的命令帮助。

以用户www-data在本机localhost的9000端口下运行一个PHP FastCGI进程，输入以下命令

_/usr/bin/spawn-fcgi -a 127.0.0.1 -p 9000 -u www-data -g www-data -f /usr/bin/php5-cgi -P /var/run/fastcgi-php.pid_

加入开机运行，以免每次开机运行此命令。

_vi /etc/rc.local_

在最后一行加入下面语句（在exit前面）。

[...]

/usr/bin/spawn-fcgi -a 127.0.0.1 -p 9000 -u www-data -g www-data -f /usr/bin/php5-cgi -P /var/run/fastcgi-php.pid

[...]

4.安装 MySQL 数据库：

sudo apt-get install mysql-server

sudo apt-get install mysql-client

5.链接phpmyadmin:

sudo mv /usr/share/phpmyadmin/ /usr/share/nginx/www/






* * *








至此安装完毕。当然，不同机子肯定会有不一样的问题，大家可以在评论里交流安装过程中的心得。祝大家安装顺利！
