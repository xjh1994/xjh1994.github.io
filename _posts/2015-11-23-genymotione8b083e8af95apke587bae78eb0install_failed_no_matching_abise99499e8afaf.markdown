---
author: xjh1994
comments: true
date: 2015-11-23 03:31:58+00:00
layout: post
slug: genymotion%e8%b0%83%e8%af%95apk%e5%87%ba%e7%8e%b0install_failed_no_matching_abis%e9%94%99%e8%af%af
title: Genymotion调试APK出现INSTALL_FAILED_NO_MATCHING_ABIS错误
wordpress_id: 590
categories:
- 安卓
tags:
- Android
- Genymotion
- 模拟器
- 调试
---

由于APK中使用了native libraries，库不支持Genymotion的cpu的体系结构，导致安装失败。

解决：下载支持库[http://download.csdn.net/detail/wjr2012/9017005](http://download.csdn.net/detail/wjr2012/9017005)（支持5.1系统）



转自：http://blog.csdn.net/wjr2012/article/details/16359113
