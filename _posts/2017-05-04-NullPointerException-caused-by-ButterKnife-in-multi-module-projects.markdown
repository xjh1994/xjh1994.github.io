---
author: xjh1994
comments: true
date: 2017/5/4 12:15:27
layout: post
slug: NullPointerException-caused-by-ButterKnife-in-multi-module-projects
title: 组件化多Module工程使用ButterKnife时出现注解ID混乱导致NullPointerException
categories:
- Java
- 原创
- 安卓
tag:
- Android
- 组件化
---

> “组件化是坑，不得已而为之！”   ——鲁迅

在进行一个组件化项目时，昨天还好好的代码，今天各种报空指针闪退，看了一下Log，都是 `Required view 'XXX' with ID XXX for field 'XXX' was not found. ...`之类的错误。点进去看一下ButterKnife生成的文件，发现查找的id名跟实际的根本不匹配，怀疑是ButterKnife的Bug；网上搜了一遍没有发现解决方案，于是去GitHub上翻Issue，一会儿就找到了。

Issue链接： [ButterKnife generates ViewBinding class with wrong resource ID #779](https://github.com/JakeWharton/butterknife/issues/779)

确实是ButterKnife的Bug：**在多Module工程中，如果一个使用了ButterKnife的Module依赖了另外一个使用了ButterKnife的Module，就会产生异常。原来int类型的资源ID，跨Module时会冲突，需要加上包名来区分它们。**

**解决方案**

这个Bug已经在 `8.5.2-SNAPSHOT` 版本中被修复了，只要更新ButterKnife到这个版本就可以解决问题。

```gradle
buildscript {
    repositories {
        ...
        jcenter()
        maven { url 'https://oss.sonatype.org/content/repositories/snapshots' }
    }
    dependencies {
        ...
        classpath 'com.jakewharton:butterknife-gradle-plugin:8.5.2-SNAPSHOT'
    }
}
...
apply plugin: 'com.android.library'
apply plugin: 'com.jakewharton.butterknife'
...
repositories {
    ...
    jcenter()
    maven { url 'https://oss.sonatype.org/content/repositories/snapshots' }
}
dependencies {
    ...
    compile 'com.jakewharton:butterknife:8.5.2-SNAPSHOT'
    annotationProcessor 'com.jakewharton:butterknife-compiler:8.5.2-SNAPSHOT'
}
```

想看源码的点这里：

解决Bug的PullRequest：[Scope symbol IDs per element package name](https://github.com/JakeWharton/butterknife/pull/788)
