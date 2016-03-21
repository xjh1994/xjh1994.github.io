---
author: xjh1994
comments: true
date: 2015-11-30 11:29:54+00:00
layout: post
slug: bmob-exception-on-genymotion-5-0-null-bluetooth-binder-is-null
title: Bmob 在Genymotion5.0模拟器上调试APK出现错误：Bluetooth binder is null
wordpress_id: 593
categories:
- 原创
- 安卓
tags:
- '5.0'
- Android
- Bmob
- Genymotion
- 'Null'
- 权限
- 模拟器
---

AS后台Log显示错误信息：

    
    BluetoothAdapter: Bluetooth binder is null


原来是由于模拟器没有蓝牙设备，而权限获取申请了蓝牙权限。

解决方案：注释掉**AndroidManifest.xml**以下内容

    
    
    <uses-permission android:name="android.permission.BLUETOOTH"></uses-permission>
    <uses-permission android:name="android.permission.BLUETOOTH_ADMIN"></uses-permission>
