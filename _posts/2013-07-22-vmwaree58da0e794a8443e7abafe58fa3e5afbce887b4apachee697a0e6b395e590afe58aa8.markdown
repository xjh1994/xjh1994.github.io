---
author: xjh1994
comments: true
date: 2013-07-22 14:18:31+00:00
layout: post
slug: vmware%e5%8d%a0%e7%94%a8443%e7%ab%af%e5%8f%a3%e5%af%bc%e8%87%b4apache%e6%97%a0%e6%b3%95%e5%90%af%e5%8a%a8
title: Vmware占用443端口导致apache无法启动
wordpress_id: 477
categories:
- 未分类
---

重装xampp以后，发现apache无法启动。提示：

`Problem detected!
22:06:15 [Apache] Port 443 in use by ""C:\Program Files\VMware\VMware Workstation\vmware-hostd.exe" -u "C:\ProgramData\VMware\hostd\config.xml"" with PID 5920!
22:06:15 [Apache] Apache WILL NOT start without the configured ports free!
22:06:15 [Apache] You need to uninstall/disable/reconfigure the blocking application
22:06:15 [Apache] or reconfigure Apache and the Control Panel to listen on a different port`

明显是VMware占用了端口，如果没有以上提示，可以用如下步骤检查：
`首先用命令行检查下XAMPP目录下apache_start.bat，出现如下情况：
D:Program Filesxampp>apache_start.bat Diese Eingabeforderung nicht waehrend des Running beenden Bitte erst bei einem gewollten Shutdown schliessen Please close this command only for Shutdown Apache 2 is starting ... (OS 10048)通常每个套接字地址(协议/网络地址/端口)只允许使用一次。 : make_sock: could not bind to address 0.0.0.0:443 no listening sockets available, shutting down Unable to open logs Apache konnte nicht gestartet werden Apache could not be started 请按任意键继续. . .
`
[![MATRIX-WALLPAPER-2-by-STEELGOHST](http://www.codesth.com/wp-content/uploads/2013/07/MATRIX-WALLPAPER-2-by-STEELGOHST-300x187.jpg)](http://www.codesth.com/wp-content/uploads/2013/07/MATRIX-WALLPAPER-2-by-STEELGOHST.jpg)
如上图在VMware里修改一下就OK了，要么关闭VMware的共享，要么改端口！
