---
author: xjh1994
comments: true
date: 2013-06-18 14:15:16+00:00
layout: post
slug: '%e3%80%90%e4%b8%aa%e4%ba%ba%e5%bb%ba%e7%ab%99%e3%80%91linode-vps-nginx-php5-mysql-wordpress'
title: 【个人建站】Linode vps + Nginx + PHP5 + MySQL + WordPress
wordpress_id: 292
categories:
- Linux
- Mac
- MySQL
- PHP&amp;MySQL
- WordPress
- 原创
- 开源项目
- 数据库
tags:
- Apache
- FastCGI
- Linux
- MySQL
- Nginx
- PHP
- WordPress
- 网站
---

![https://www.linode.com/images/linode_logo_gray.png](https://www.linode.com/images/linode_logo_gray.png)linode_logo




搭建个人站点，大致需要做这么几件事情：



	
  * 一台具备公网IP的服务器

	
  * 安装操作系统，搭建环境

	
  * 购买域名，域名绑定IP

	
  * 部署应用程序




# 服务器


在VPS的选择上，我用的是Linode。Linode是一家来自于米帝的专注于提供 Linux VPS 的服务提供商， 虚拟化技术采用了Xen，Linode的含义是Linux Node。

Linode在国内外口碑都不错，价格适中，质量可靠，童叟无欺。Linode提供了各种Linux操作系统供选择，比如Ubuntu、Redhat、Debian、CentOS等等，装系统和重装系统都非常简单。

好，我们下面简单说一下步骤，访问[https://manager.linode.com/session/signup](https://manager.linode.com/session/signup)
填写邮箱、用户名密码，就算注册成功了，Linode会给你发封邮件确认，打开那个确认连接，大家就会看到下面这张图的内容：

[![website1](http://macshuo.com/wp-content/uploads/2013/06/website1-300x135.png)](http://macshuo.com/wp-content/uploads/2013/06/website1.png)

Linode通过它的ticket system（一套支持系统）提供7 x 24 x 365的支持服务，不是7 x 24 x 365的不停机服务，另外Linode还提供了4小时的免费试用服务，比较厚道，如果你试试觉得不爽还可以选择不玩。

选择继续，就可以选机房了，Linode目前提供了东京和欧美等地的机房选择，我选了东京机房，据说是针对亚太地区用户的需求新开辟的，速度很快。然后选操作系统，设置硬盘大小、root密码等，点击「Rebuild」，你就进入了VPS的控制台，等Host Job Queue的所有任务都是绿色的Success，就可以点击「Boot」，启动系统。然后找到Remote Access这个标签，点进去就可以找到这台服务器的访问IP，打开终端，输入ssh root@x.x.x.x，就可以登录系统了，看到了吧，very simple！

试用之后，如果你觉得可以，点击Acount标签，完善自己的信息，选择服务器配置，支付信息，然后就可以完整支付流程了。

好，服务器部分就介绍到这里。以下是我的linode推荐码，如果大家要购买Linode服务，可以用这个链接。

[http://www.linode.com/?r=6bd100da844d8d2c191680a4792610467ce9052](http://www.linode.com/?r=6bd100da844d8d2c191680a4792610467ce9052)


# 搭建环境




<blockquote>我选用的服务器是Ubuntu12.04，64位。以下内容均基于该环境描述。</blockquote>


1、创建用户

第一次登录需要root用户，什么是root？root就是整个Linux操作系统最牛逼的主，他想干嘛就干嘛，他想删谁就删谁，如果用root执行一下rm -rf，那整个锡安就会被抹掉，尼奥也拯救不了，如果root愿意，他可以抹掉你曾经存在过的所有痕迹。所以，我们不能没事就用root进去耍，为了解决这个问题，我们必须要建立一个agent，平时是普通用户，关键时刻充当root的角色。

具体操作如下：

首先用root登录系统

    
    <code>ssh root@x.x.x.x</code>


创建一个新用户，用户名随你喜欢，比如叫做xjh1994

    
    <code>adduser mactalk</code>


按照提示信息输入密码和相关信息，就可以完成操作。完成之后系统就会自动建立/home/xjh1994路径。

然后是授权，输入

    
    <code>visudo</code>


在编辑器中找到如下内容：

    
    <code>root    ALL=(ALL:ALL) ALL</code>


在下面加一行

    
    <code>mactalk    ALL=(ALL:ALL) ALL</code>


通过ctrl+x保存退出即可。然后就可以退出root，用mactalk重新登录（ssh xjh1994@x.x.x.x），登录进来默认目录在/home/mactalk下，当你想行使root权限时，请在命令之前增加sudo，按照系统提示输入密码即可执行操作。


# 域名和DNS


要建站，必须要有域名。能够提供域名的厂商很多，国内外都有。不过我强烈推荐大家购买国外厂商的域名，免去提交材料和备案之苦，国外动动鼠标和小手分分钟搞定的事情，国内要提交各种材料、备案、定期监管balabala……

国外的域名厂商推荐www.godaddy.com和www.name.com，都不错。我使用的是国内的万网。

万网

在域名选择上，最好满足这几点要求：有意义、好记、简短，另外尽可能使用com（通用顶级域名）。申请步骤也很简单，访问www.godaddy.com，在搜索框输入你想要购买的域名，点击搜索，你会看到这个域名的具体信息，是否被使用，相关域名，价格等信息，域名后缀一般有com、net、me、us、info等，建议选com，不建议选info，据说info结尾的网站大部分是垃圾网站，会被搜索引擎屏蔽。

选好域名后，点添加，加入购物车，如果不需要其他服务，一路下一步即可，最后设置支付信息，交钱吧。

购买完成之后，进入万网的域名管理控制台，找到你购买的域名，把域名和你的IP地址绑定起来，就可以通过域名访问你的网站了。这里就涉及到DNS了。

DNS的洋名一般说成Domain Name System，就是给域名提供服务的。光有域名没用，还得有相关的服务能够把域名解析成IP地址才行，DNS就干这事。

万网默认提供了DNS服务，点击会员中心–域名–域名解析，在弹出的设置面板中设置你的网站IP即可，具体的图文教程网络上很多。因为购买了Linode服务，我最后采用了Linode的DNS，具体的做法是：



	
  1. 登录linode.com，点击DNS Manager标签，进入管理控制台

	
  2. 选择Add a domain zone

	
  3. 填写域名、邮件地址

	
  4. 点击Add a Mater Zone，就算完成了


最后一步就是在万网的控制台里设置一下Linode的DNS服务器，很简单就不描述了。


# 应用程序和部署


针对网站提供的服务不同，需要不同的技术选型，我的需求就是做个风格简约的博客，用来存放MacTalk的文章，同时有个地方能够随意发表一些个人观点，就这么简单，所以针对这个需求进行选择即可。大家将来建站的时候也是一样，明确自己的需求，不要为未来买单，尽量搞的轻量级一些，最忌讳给的是龙套的钱，您自个却按照男猪脚进行角色扮演，不提倡。

搭建轻量级的博客不建议使用.Net或JavaEE的技术，这些技术都比较重，必要性不大。Php、Python、Ruby相关的框架都是可选的技术。因为我对Python相对熟悉一些，最初想找个开源的Python Blog框架，不过后来综合对比了一下，发现在个人博客领域，WordPress基本上无出其右，技术成熟、安装方便、性能稳定、插件众多，实在是居家建站、个人扯淡之必备良药，就是它了。

在确定了基本需求和工具之后，我们看看涉及到哪些技术：

1、Nginx Nginx是一款高性能的HTTP服务器软件，由俄罗斯的一位大牛Igor Sysoev开发的，源代码以类BSD许可证的形式发布。Nginx的设计非常轻量级，由内核和模块组成，内核微小简洁，模块功能强大，静态编译。Nginx做的事情简单来说就是，接收客户端（浏览器）的HTTP请求，然后通过映射机制把不同类型的请求交给不同的模块去处理，比如html、图片、css等可以交给静态资源模块处理，还可以做压缩、缓存等，php、python等类型的请求则交给FastCGI模块去处理，完成业务逻辑。

什么是FastCGI呢？这玩意就等于是HTTP服务器和动态脚本语言通信的接口，就像一个粘合剂一样把HTTP请求和动态脚本处理整合在一起，顾名思义，处理速度非常Fast！

Nginx可以说是HTTP服务器软件市场的新贵，目前国内很多大型网站都采用了Nginx作为默认的web服务器，比如阿里、腾讯、新浪等等，国外就更多了。

那么Nginx比Apache优秀在哪呢？



	
  * Nginx的所有模块都是全静态编译的，启动Nginx后，Nginx的模块被自动加载，静态库执行效率更高。

	
  * Nginx支持epoll（Linux系列）和kqueue（BSD系列）I/O事件通知机制。完，又特么出现两个名词！这让人情何以堪、文何以完啊？简单说说epoll吧。epoll是Linux2.6正式引入的提高网络I/O的处理方法，它的几个优点是：单一进程打开的FD（文件描述符）数量仅受限于操作系统，1GB内存的机器上大约是10万左右，这一点大大提升了处理海量请求的能力；采用共享内存的模式避免内存拷贝；随着打开FD的数量增加，I/O效率不会线性下降。总之，大家知道epoll很牛逼就是了。

	
  * Nginx支持多进程的工作方式，Nginx启动后会有一个master进程，多个worker进程。worker进程一般对应服务器的CPU数量，你有个8核的CPU，最好把worker设置为8。master负责接收外界信号，并向worker发送信号，监控worker的运行状况，当worker挂掉的时候，启动新的worker。写到这我发现，这特么活脱脱就是一个地主老财打压长工的模式啊！
尤其是Nginx的不中断重启机制，当系统配置变化需要重新启动Nginx时，我们就给地主（master）发个消息，说这批长工（worker）太老了，都得换掉，你看着办。地主收到消息后就开始偷偷雇佣新的长工（worker），然后假惺惺的告诉老长工，把手头的活干完就行了，别太累了，啊。这时候如果有新的请求，就会交给新长工干，等所有的老长工把活都干完了，就直接fire，绝不留情。这样，整个服务无中断重启过程就完成了，就特么一个字，黑！


Nginx功能非常强大，一本书也写不完，我简单就说这么几句。老话，有兴趣的，用Google百度一下！

大概了解了Nginx的工作机制，下面安装就比较简单了，Nginx可以编译安装，也可以在线安装，对于普通用户来说，使用apt-get在线安装即可，省的自己去找依赖关系。

    
    <code>#安装
    sudo apt-get install nginx
    #启动
    sudo service nginx start</code>


如果安装和启动都没有问题，我们再调整几个参数就可以了。

找到/etc/nginx/nginx.conf，做以下几个改动：



	
  * 把worker_processes设置为服务器的CPU核数（查看几核命令：cat /proc/cpuinfo |grep “cores”|uniq）

	
  * 在event里增加use epoll

	
  * 把worker_connections的值设置大一点，如果是1G内存，不要大于100000/worker_processes。


其他的采用默认值即可，然后重新加载参数：

    
    <code>sudo nginx -s reload</code>


好，Nginx就算妥了，后续在安装PHP和WordPress时还要做一些配置。

2、MySQL

MySQL是应用最为广泛的开源数据库，这个没什么可说的，非常成熟的技术，直接安装即可：

    
    <code>sudo apt-get install mysql-server</code>


安装过程中，MySQL会提示你设置root密码（root的作用参考之前介绍的，把操作系统换成数据库即可）。如果安装时没设置密码，等MySQL起来后用mysqladmin改也行，用sql改也行，简单不啰嗦。

3、PHP

WordPresss是基于PHP开发的，所以我们得为WordPress准备好环境，安装PHP。

    
    <code>sudo apt-get install php5
    sudo apt-get install php5-fpm</code>


php5-fpm是PHP FastCGI的实现之一，能够更好的管理PHP进程，控制内存使用，平滑重载等，现在我们都用它！

下面做一点简单配置，打开php.ini文件：

    
    <code>sudo vim /etc/php5/fpm/php.ini</code>


找到cgi.fix_pathinfo=1这一行，把1改为0。 值为1时，php的解释器会尽可能的去解析客户端请求的文件各种类型，这会引发一些安全漏洞，设置为0时，解释器只会去解析特定的文件类型，设置为0是一种相对安全的处理策略。

修改www.conf：

    
    <code>sudo vim /etc/php5/fpm/pool.d/www.conf</code>


把 `listen = 127.0.0.1:9000` 修改为 `listen = /var/run/php5-fpm.sock`，前者是走TCP socket，后者是Unix domain socket，如果服务都在同一台机器上，建议使用后者，效率更好一些。

重新启动PHP，这部分的配置就算完成了：

    
    <code>sudo service php5-fpm restart</code>


4、WordPress

首先下载WordPress的最新版本，我用了中文版，下载和解压缩：

    
    <code>wget http://cn.wordpress.org/wordpress-3.5.1-zh_CN.tar.gz
    tar -xzvf wordpress-3.5.1-zh_CN.tar.gz </code>


在MySQL中为WordPress创建用户和数据库，这部分很简单就不描述了，后续会在macshuo.com网站上补充。我们设定数据库为wordpress，用户名为mactalk，并且把数据库编码改为UTF-8。

在解压好的wordpress文件夹下，执行：

    
    <code>cp wp-config-sample.php wp-config.php
    vim ~/wordpress/wp-config.php</code>


按照文件内容注释填写数据库名称、用户名、密码、数据库编码使用UTF-8，然后保存退出。

为wordpress创建www文件夹，并且把完整的wordpress目录复制到www文件夹下，并设置相关权限：

    
    <code>sudo mkdir -p /var/www
    
    sudo cp -r ~/wordpress/* /var/www
    
    cd /var/www/
    
    sudo chown www-data:www-data * -R 
    
    sudo usermod -a -G www-data username</code>


安装php的MySQL驱动

    
    <code>sudo apt-get install php5-mysql</code>


设置虚拟主机：

在/etc/nginx/sites-available下创建文件wordpress

    
    <code>sudo vim wordpress</code>


找到并修改以下部分，修改完如下：

** location / {**

**                root   /var/www/;**

**                index index.html index.htm ****index.php;**

**        }**

** location ~ .php$ {**

**                fastcgi_pass   unix:/var/run/php5-fpm.sock;**

**                fastcgi_index  index.php;**

**                fastcgi_param  SCRIPT_FILENAME  /var/www/nginx-default$fastcgi_script_name;**

**                include        fastcgi_params;**

**        }**

** **

这个文件的作用就是把Nginx和WordPress粘合在一起，接收客户端的请求并反馈响应结果。有几点要注意的是，root设置为/var/www/，index部分增加index.php，fastcgi_pass对应之前设置的unix socket：unix:/var/run/php5-fpm.sock。

为wordpress文件建立软连接：

    
    <code>sudo ln -s /etc/nginx/sites-available/wordpress /etc/nginx/sites-enabled/wordpress</code>


最后重新启动nginx和php5-fpm，就算大功告成了：

    
    <code>sudo service nginx restart 
    
    sudo service php5-fpm restart</code>


如果一切正常的话，访问你的域名或者公网IP，就可以看到wordpress的提示页面，根据信息提示初始化数据库，创建管理员，基本框架就算建好了，之后就是完善和优化，比如性能优化、主题选择、配置信息、插件选择、扩展开发等等，大家慢慢体会吧。

转自[http://macshuo.com/?p=547](http://macshuo.com/?p=547)，有删改。
