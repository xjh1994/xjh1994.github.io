---
author: xjh1994
comments: true
date: 2013-04-27 04:51:16+00:00
layout: post
slug: '%e3%80%90php%e3%80%91%e5%87%ba%e7%8e%b0cannot-modify-header-information%e9%97%ae%e9%a2%98%e7%9a%84%e8%a7%a3%e5%86%b3%e6%96%b9%e6%b3%95'
title: 【PHP】出现Cannot modify header information问题的解决方法
wordpress_id: 132
categories:
- PHP&amp;MySQL
- WordPress
- 原创
- 编程
tags:
- Cannot modify header information
- 解决
---

Warning: Cannot modify header information - headers already sent by....







这样的语句，很显然,造成这个原因是因为setcookie造成的,查了一下网上,有如下的解释: cookie本身在使用上有一些限制，例如：
1.呼叫setcookie的敘述必須放在<html>标签之前
2.呼叫setcookie之前，不可使用echo
3.直到網頁被重新載入後，cookie才會在程式中出現
4.setcookie函数必須在任何資料輸出至浏览器前，就先送出
5.……
基於上面這些限制，所以執行setcookie（）函数时，常會碰到"Undefined index"、"Cannot modify header information - headers already sent by"…等問題，解決"Cannot modify header information - headers already sent by"这个錯誤的方法是在产生cookie前，先延缓資料输出至浏览器，因此，您可以在程式的最前方加上ob_start（）；这个函數。这样就可以解决 了。
于是看看后面跟的那句"output started at...."意思是在setcookie之前已经在另一处有输出了,于是找到output started at后面跟的那个文件,看到第一行是空白的,然后才是<?php 这样开始,难道会是这一行的问题吗??我本地也有这一行呢,去掉,刷新再试,不再提示warning了
解决完毕!
**解决方法二：**
找到php.ini 这个配置文件，然后查找一项：output_buffering将其值由原来的off改为on，重新启动Apache就ok了。
