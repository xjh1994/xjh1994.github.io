---
author: xjh1994
comments: true
date: 2016-01-08 03:02:19+00:00
layout: post
slug: attribute-ripplecolor-has-already-been-defined-in-android-studio
title: “Attribute ”rippleColor“ has already been defined” in Android Studio
wordpress_id: 603
categories:
- 安卓
tags:
- Android
- 第三方库
---

引入第三方库时Gradle编译出错，提示“Attribute ”rippleColor“ has already been defined” 。检查了一下自己的color.xml。并没有定义这个属性，那么应该就是第三方库里使用了这个属性。

网上搜了一下，发现是MaterialDesignLibrary这个库的坑。因为用的是1.5aar版本，改成1.6即可。
即把
    
    compile 'com.github.navasmdc:MaterialDesign:1.5@aar'

改成
    
    compile 'com.github.vajro:MaterialDesignLibrary:1.6'


Github有人提了这个issue，官方升级之后修复了。[https://github.com/navasmdc/MaterialDesignLibrary/issues/289](https://github.com/navasmdc/MaterialDesignLibrary/issues/289)
[MaterialDesignLibrary Github地址](https://github.com/vajro/MaterialDesignLibrary)
但是改了之后又出现新的问题，这个库的最低版本支持是16，而我的项目最低是14，所以要在AndroidManifest.xml中加一行


    
    <uses-sdk tools:overridelibrary="冲突库的包名"></uses-sdk>



问题解决。以后引入第三方库要小心了，不能什么库都用，要看质量。
