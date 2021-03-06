---
author: xjh1994
comments: true
date: 2013-07-11 22:57:20+00:00
layout: post
slug: linux-root-password
title: 【Linux】各个Linux版本的本地root密码破解方法
wordpress_id: 316
categories:
- Linux
- 操作系统
tags:
- Linux
- Root
- 密码
- 破解
---

![](http://photocdn.sohu.com/20120105/Img331254178.jpg)

这段时间老碰到有人问及各个linux版本的本地root密码破解方法，我这里自己以及在网络上搜集了些资料，希望对看到了这文章而又恰好用得到的技术人员有点帮助：

（一）RedHat/CentOS/Fedora 系统密码破解

1.在grub选项菜单按E进入编辑模式

2.编辑kernel 那行最后加上S (或者Single）

3.按B，启动到single-user mode

4.进入后执行下列命令



	
  * # mount -t proc proc /proc

	
  * # mount -o remount,rw /

	
  * #passwd

	
  * #sync

	
  * #reboot


（二）Debian linux 系统密码破解

1.在grub选项菜单'Debian GNU/Linux,...(recovery mode)'，按e进入编辑模式

2.编辑kernel那行最后面的 ro single 改成 rw single init=/bin/bash，按b执行重启

3.进入后执行下列命令

	
  * #mount -a

	
  * #passwd root

	
  * #reboot


（三）Freebsd 系统密码破解

1.开机进入引导菜单

2.选择每项(按4)进入单用户模式

3.进入之后输入一列命令

	
  * root@#mount -a

	
  * root@#fsck -y

	
  * root@#passwd(修改密码命令)

	
  * root@#root(要破解密码的用户名)

	
  * Enter new unix password:

	
  * root@#init 6 (重启)


（四）Solaris 系统密码破解

1.在grub选项菜中选择solaris failasfe 项

2.系统提示Do you wish to have it mounted read-write on /a ?[y,n,?] 选择y

3.就进入单用户模式

4.输入下列命令:passwd

[root@#init](mailto:root@#init) 6 (重启)

（五）NetBsd 系统密码破解

1.开机：当出现提示符号并开始倒数五秒时， 键入以下指令：

> boot -s (进入单用户模式命令)

2.在以下的提示符号中

Enter pathname of shell or RETURN for sh:

按下 Enter。

3.键入以下指令：



	
  * # mount -a

	
  * # fsck -y


4.使用 passwd 更改 root 的密码。

5.使用 exit 指令进入多人模式。

（六）SUSE 系统密码破解

1.重新启动机器，在出现grub引导界面后，在启动linux的选项里加上init=/bin/bash，通过给内核传递init=/bin/bash参数使得OS在运行login程序之前运行bash，出现命令行。

2.稍等片刻出现(none)#:命令行。

3.这时输入mount -n / -o remount,rw 表示将根文件系统重新mount为可读写，有了读写权限后就可以通过passwd命令修改密码了。

4.这时输入passwd命令就可以重置密码了

5.修改完成后记得用mount -n / -o remount,ro将根文件系统置为原来的状态。

原文地址：[http://os.51cto.com/art/200910/159523.htm](http://os.51cto.com/art/200910/159523.htm)
