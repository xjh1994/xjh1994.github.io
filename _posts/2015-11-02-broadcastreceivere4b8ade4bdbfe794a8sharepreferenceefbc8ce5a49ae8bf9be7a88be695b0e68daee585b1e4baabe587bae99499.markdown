---
author: xjh1994
comments: true
date: 2015-11-02 06:03:58+00:00
layout: post
slug: broadcastreceiver%e4%b8%ad%e4%bd%bf%e7%94%a8sharepreference%ef%bc%8c%e5%a4%9a%e8%bf%9b%e7%a8%8b%e6%95%b0%e6%8d%ae%e5%85%b1%e4%ba%ab%e5%87%ba%e9%94%99
title: BroadcastReceiver中使用Sharepreference，多进程数据共享出错
wordpress_id: 566
categories:
- 未分类
---

**问题描述：**
在做一个开关修改配置的安卓程序中，在Activity中修改Sharepreference，到BroadcastReceiver中无法获取正确的值，一直都是修改前的数值。猜测是由于多个进程之间共享数据的问题，百度了一下果然是。

**解决方法：**
将SharedPreference的**MODE**设置为：**MODE_MULTI_PROCESS**。

例如：
**SharedPreferences sp = context.getSharedPreferences(PREFERENCE_NAME, Context.MODE_WORLD_READABLE | Context.MODE_MULTI_PROCESS);**

<!-- more -->

MODE_MULTI_PROCESS的说明：


<blockquote>SharedPreference loading flag: when set, the file on disk will be checked for modification even if the shared preferences instance is already loaded in this process. This behavior is sometimes desired in cases where the application has multiple processes, all writing to the same SharedPreferences file. Generally there are better forms of communication between processes, though.
This was the legacy (but undocumented) behavior in and before Gingerbread (Android 2.3) and this flag is implied when targetting such releases. For applications targetting SDK versions greater than Android 2.3, this flag must be explicitly set if desired.

也就是说，MODE_MULTI_PROCESS这个值是一个标志，在Android 2.3及以前，这个标志位都是默认开启的，允许多个进程访问同一个SharedPrecferences对象。而以后的Android版本，必须通过明确的将MODE_MULTI_PROCESS这个值传递给mode参数，才能开启多进程访问。</blockquote>
