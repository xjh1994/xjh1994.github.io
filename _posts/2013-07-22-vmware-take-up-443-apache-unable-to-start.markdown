---
author: xjh1994
comments: true
date: 2013-07-22 14:20:35+00:00
layout: post
slug: vmware-take-up-443-apache-unable-to-start
title: Vmware占用443端口导致apache无法启动
wordpress_id: 335
categories:
- 系统工具
- 趣闻轶事
- 软件
- 软件应用
tags:
- '443'
- Apache
- VMware
- 端口
---

重装xampp以后，发现apache无法启动。提示：

`Problem detected!
22:06:15 [Apache] Port 443 in use by ""C:Program FilesVMwareVMware Workstationvmware-hostd.exe" -u "C:ProgramDataVMwarehostdconfig.xml"" with PID 5920!
22:06:15 [Apache] Apache WILL NOT start without the configured ports free!
22:06:15 [Apache] You need to uninstall/disable/reconfigure the blocking application
22:06:15 [Apache] or reconfigure Apache and the Control Panel to listen on a different port`

明显是VMware占用了端口，如果没有以上提示，可以用如下步骤检查：
`首先用命令行检查下XAMPP目录下apache_start.bat，出现如下情况：
D:Program Filesxampp>apache_start.bat Diese Eingabeforderung nicht waehrend des Running beenden Bitte erst bei einem gewollten Shutdown schliessen Please close this command only for Shutdown Apache 2 is starting ... (OS 10048)通常每个套接字地址(协议/网络地址/端口)只允许使用一次。 : make_sock: could not bind to address 0.0.0.0:443 no listening sockets available, shutting down Unable to open logs Apache konnte nicht gestartet werden Apache could not be started 请按任意键继续. . .
`
[![Apache](http://wwwxjh-wordpress.stor.sinaapp.com/uploads/2013/09/100K62103-0_lit.png)](http://wwwxjh-wordpress.stor.sinaapp.com/uploads/2013/09/100K62103-0_lit.png)
如上图在VMware里修改一下就OK了，要么关闭VMware的共享，要么改端口！
