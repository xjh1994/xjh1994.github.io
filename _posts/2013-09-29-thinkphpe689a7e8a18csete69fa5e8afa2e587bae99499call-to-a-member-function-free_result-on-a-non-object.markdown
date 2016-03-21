---
author: xjh1994
comments: true
date: 2013-09-29 00:30:08+00:00
layout: post
slug: thinkphp%e6%89%a7%e8%a1%8cset%e6%9f%a5%e8%af%a2%e5%87%ba%e9%94%99call-to-a-member-function-free_result-on-a-non-object
title: ThinkPHP执行SET查询出错Call to a member function free_result() on a non-object
wordpress_id: 494
categories:
- 未分类
---

最近在做社团网站的后台，用的是ThinkPHP框架。在有个Model里执行如下的SQL语句是出错，提示_**Call to a member function free_result() on a non-object**_

    
    M()->query("SET OPTION SQL_QUOTE_SHOW_CREATE = 1"); //1，表示表名和字段名会用``包着的,0 则不用``


[![free_result](http://bcs.duapp.com/blogxjh/blog/free_result.jpg)](http://bcs.duapp.com/blogxjh/blog/free_result.jpg)

经多方查找后找到原因，但还未测试，贴出来防止以后再遇到。

原因：数据库版本问题。
我的MySQL-Client版本为5.3.3，安装5.6及以上版本并且和Server端一致，问题就消失了。
