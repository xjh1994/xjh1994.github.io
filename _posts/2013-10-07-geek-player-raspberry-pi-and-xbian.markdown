---
author: xjh1994
comments: true
date: 2013-10-07 11:40:57+00:00
layout: post
slug: geek-player-raspberry-pi-and-xbian
title: 极客播放器—树莓派联合xbian打造客厅电视盒
wordpress_id: 500
categories:
- 未分类
---

xbian系统目前刚刚升级到1.0 Alpha版本，树莓派搭载xbian系统就是一个HTPC了。互联网的大佬们也认识到了占领客厅的重要性了，下一个阵地就是把液晶电视通过“盒子”之类的东西联系起来，通过大屏幕分享网络音视频资源、同时可以扩展手机和平板的显示内容，这是个发展方向，毋庸置疑的了。

   下载xbian的镜像文件，官方地址：[http://www.raspbmc.com/download/](http://www.raspbmc.com/download/)

   写入到树莓派，使用工具和过程与安装别的系统一样。

    启动速度很快，第一步当然是把英文界面变成汉语，设置步骤就2步：首先鼠标依次点击 【SYSTEM】-【Settings】-【Appearance】-【Skin】，在右侧选择【Font】，翻页选中【Arial based】，稍等几秒钟；第二步是【Appearance】-【International】-在右侧选择【Language】，翻页选中【Chinese (Simple)】，稍等几秒钟，画面就是汉语的了。如果操作反了的话，哈哈，你就别想看清楚界面了。

   想收看国内的视频网站和电视直播，只要安装视频插件库就可以了。推荐一个HDPfans，这儿有详细的安装步骤[http://bbs.htpc1.com/thread-312488-1-1.html](http://bbs.htpc1.com/thread-312488-1-1.html)，基本上就是选择【系统设置】 -> 【扩展功能】-->【选择从zip文件安装】，选择下载好的zip文件就可以了。这只是安装了插件库，还差一步安装具体的插件，选择【获取扩展功能】，保证联网的情况下，就可以看到各个视频插件了，挨个点击安装吧。完事了就回到主界面选择视频-->扩展功能，就可以看你想看的节目了。

    第二个推荐的视频插件库是Chinese Add-on Repository for XBMC Eden ，下载地址[http://xbmc-addons-chinese.googlecode.com/files/repository.googlecode.xbmc-addons-chinese-eden.zip](http://xbmc-addons-chinese.googlecode.com/files/repository.googlecode.xbmc-addons-chinese-eden.zip)，这个内容更丰富的。值得安装！热门电影、电视剧、美剧和娱乐一应俱全！

    有个细节值得提一下：最好安装完xbain系统后，在windows系统下直接下载上述插件到SD卡的根目录下，这样选择安装插件库文件的时候就去找boot目录！

附：【HDPfans插件库安装方法】

目前HDP插件库已经聚合了HDP直播，HDP搜狐影视，178Dota视频等内容，获得了XBMC官方开发团队的技术支持，后续会有更多更好的插件发布，您只需要将HDP插件库安装到您的xbmc就能享受到不断更新和增加的hdpfans们提供的插件了。

1、下载上面的安装文件，得到repository.hdpfans.xbmc-addons.zip这个文件，注意不需要解压缩！
2、如果是安装到手机或者平板上的xbmc里，请把上述那个文件拷贝到sd卡插入手机或平板。
3、下面是进入xbmc后的操作：

     1）第一次进入xbmc是英文版的，需要做如下操作进入中文界面，进入system->appearance

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164400ug2dqqdzkgww2sqs.jpg.thumb.jpg)

     2)  选择skin，把fonts设置为arial based，这步很关键，不改fonts的话会导致中文字符无法显示。

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164401asny7ysb8qmdqfsz.jpg.thumb.jpg)

     3）到international里面设置lanuage为Chinese(simple)

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164402sw44kqpwp3pb4p49.jpg.thumb.jpg)

    4）系统语言设置好后，接下来就是安装插件了，进入 系统设置 -> 扩展功能

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164403kd4suu0h4dta0kda.jpg.thumb.jpg)

   5） 选择从zip文件安装

![](http://www.hdpfans.com/data/attachment/forum/201302/16/1644040oidvp8sjsgj803y.jpg.thumb.jpg)

   6）选择我们之前下载好的那个安装文件：repository.hdpfans.xbmc-addons.zip 就完成了插件库的安装。
   7）下面就是从HDPfans中文插件库里面选择安装你感兴趣的插件了。进入 获取扩展功能

![](http://www.hdpfans.com/data/attachment/forum/201302/16/1644049d0wwl9axdk66wen.jpg.thumb.jpg)

   8）选择HDPfans中文插件库（XBMC自带了一些其他的英文插件库）

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164405aia3j1334b4o3dbc.jpg.thumb.jpg)

   9）选择您感兴趣的插件，下面以HDP直播为例：

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164406rhdzk4xhcnvgntqg.jpg.thumb.jpg)

   10）选择安装该插件

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164407fsii1o0ojiwwpwg1.jpg.thumb.jpg)

   11） 安装好就能使用了，进入 视频 ->扩展功能

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164408rvbqo6ouzwoljwte.jpg.thumb.jpg)

   12）选择进入HDP直播

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164409nw3ortj0m08rrphn.jpg.thumb.jpg)

   13）这里是分类列表

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164409k08pncprcouunar8.jpg.thumb.jpg)

   14）可以选择源

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164410y39vay4xvby1y4yg.jpg.thumb.jpg)

    15） 这个就是播放效果了

![](http://www.hdpfans.com/data/attachment/forum/201302/16/164359oqbsmkmocc9qgkbn.jpg.thumb.jpg)

[HDPfans插件库安装文件下载地址](http://xbmc.hdpfans.com/repository.hdpfans.xbmc-addons.zip )  44.7KB

转自网络
