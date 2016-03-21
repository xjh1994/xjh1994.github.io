---
author: xjh1994
comments: true
date: 2013-09-08 03:28:07+00:00
layout: post
slug: tomcat%e5%8f%8c%e5%87%bbstartup-bat%e9%97%aa%e9%80%80
title: TomCat双击startup.bat闪退
wordpress_id: 484
categories:
- 未分类
---

[![Tomcat](http://bcs.duapp.com/blogxjh/blog/132785521.jpg)](http://bcs.duapp.com/blogxjh/blog/132785521.jpg)

昨天同学装TomCat时，下载的zip双击startup.bat结果闪退，打不开http://localhost:8080，因为他用的是XP系统，我以为是系统问题，试了好久都不能解决，于是百度了一下，得到了解决方法：

用文本编辑器打开startup.bat，可以看到里面有很多rem注释，去掉所有注释，完成以后如下



* * *






**if "%OS%" == "Windows_NT" setlocal**
** set CURRENT_DIR=%cd%**
** if not "%CATALINA_HOME%" == "" goto gotHome**
** set CATALINA_HOME=%CURRENT_DIR%**
** if exist "%CATALINA_HOME%bincatalina.bat" goto okHome**
** cd ..**
** set CATALINA_HOME=%cd%**
** cd %CURRENT_DIR%**
** :gotHome**
** if exist "%CATALINA_HOME%bincatalina.bat" goto okHome**
** echo The CATALINA_HOME environment variable is not defined correctly**
** echo This environment variable is needed to run this program**
** goto end**
** :okHome**
** set EXECUTABLE=%CATALINA_HOME%bincatalina.bat**
** if exist "%EXECUTABLE%" goto okExec**
** echo Cannot find %EXECUTABLE%**
** echo This file is needed to run this program**
** goto end**
** :okExec**
** set CMD_LINE_ARGS=**
** :setArgs**
** if ""%1""=="""" goto doneSetArgs**
** set CMD_LINE_ARGS=%CMD_LINE_ARGS% %1**
** shift**
** goto setArgs**
** :doneSetArgs**
** call "%EXECUTABLE%" start %CMD_LINE_ARGS%**
** :end**
** pause**






* * *





<blockquote>注意在批处理最后加了pause



再次双击startup，这下不是闪退而是暂停住了，提示JAVA_HOME环境变量无效，JAVA_HOME指定的是JRE目录而不是JDK目录。</blockquote>


再检查了下自定的安装目录，再打开D:Program Files,发现有个Java文件夹里有个JDK1.6.0_17。

囧，原来安装时候指定的目录是JRE的目录，JDK安装到了默认的位置了，重新指定JAVA_HOME为D:Program FilesJavaJDK1.6.0_17，path后加;D:Program FilesJavaJDK1.6.0_17/bin。。再次startup，成功，打开[http://localhost:8080](http://localhost:8080)。

另外，tomcat5.x或以上版本不需要指定以下环境变量


**CATALINA_HOME: C: Tomcat**
** CATALINA_BASE: C: Tomcat**
** TOMCAT_HOME: C:Tomcat**
** classpath=.;%JAVA_HOME%libdt.jar;%JAVA_HOME%libtools.jar;%**


转自百度空间[http://hi.baidu.com/nullmemory/item/5485fb494713a30c6cc2f0af](http://hi.baidu.com/nullmemory/item/5485fb494713a30c6cc2f0af)
