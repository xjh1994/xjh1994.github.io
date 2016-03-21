---
author: xjh1994
comments: true
date: 2013-08-09 15:08:03+00:00
layout: post
slug: java%e7%9a%84jcombobox%e8%ad%a6%e5%91%8a%e9%97%ae%e9%a2%98
title: Java的JComboBox警告问题
wordpress_id: 481
categories:
- 未分类
---

**背景：**
自定义了一个字符数组：
private String[] grades  = {"1","2","3","4","5","6","7","8","9","10"};

然后加到JComboBox中 作为下拉选项

selectCountryJComboBox = new JComboBox( countries );
编译的时候出现错误

**错误：**


<blockquote>做为原始类型JComboBox的成员JComboBox（E()）的调用
未经过检查，
JComboBox selectCountryJComboBox = new JComboBox( countries );

_ 其中，E是类型变量，E扩展已在类JComboBox中声明的Object
1个警告_</blockquote>


** 错误原因：**

在之前版本的SE中，JComboBox是javax.swing.JComboBox。在SE7中声明为泛型了，javax.swing.JComboBox<E>。
因此你需要在实例化它时指明传入指定参数类型,不然就报类型不安全的warning了。
**       解决方法：**

JComboBox<String> selectCountryJComboBox = new JComboBox<String>( countries );


