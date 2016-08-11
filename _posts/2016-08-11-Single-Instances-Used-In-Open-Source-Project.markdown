---
author: xjh1994
comments: true
date: 2016/7/22 16:25:27 
layout: post
slug: Single-Instances-Used-In-Open-Source-Project
title: 常见开源项目中使用的单例模式
categories:
- Java
- 原创
- 安卓
tag:
- Android
---

# EventBus

```
static volatile EventBus defaultInstance;

public static EventBus getDefault() {
       if (defaultInstance == null) {
           synchronized (EventBus.class) {
               if (defaultInstance == null) {
                   defaultInstance = new EventBus();
               }
           }
       }
       return defaultInstance;
   }
```