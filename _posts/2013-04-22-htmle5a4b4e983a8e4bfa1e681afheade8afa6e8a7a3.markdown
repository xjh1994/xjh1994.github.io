---
author: xjh1994
comments: true
date: 2013-04-22 10:17:29+00:00
layout: post
slug: html%e5%a4%b4%e9%83%a8%e4%bf%a1%e6%81%afhead%e8%af%a6%e8%a7%a3
title: HTML头部信息(Head)详解
wordpress_id: 47
categories:
- HTML&amp;CSS
tags:
- Head
- HTML
- 头部
---

虽然HTMl5省略了HTML文件头部冗长的标注信息，但在HTML5全面普及之前，我想我们还是有必要去彻底搞懂这些头部信息的。

HTML头部信息(head)里包含关于所在网页的信息。头部信息(head)里的内容，主要是被浏览器所用，不会显示在网页的正文内容里。

另外，搜索引擎如google,yahoo,baidu等也会查找你网页中的head信息。为了让搜索引擎能够收录你的网页，你也要填写适当的head信息。(网站被搜索引擎收录，还有其它的方法，比如被其它网站链接，这里不赘述，请浏览搜索引擎网站。)

下面说几个常用的head信息里的html元素，如标题(title)，链接(link)，样式(style)以及关于信息(meta)。


## 标题(title)


标题(title)是最常用的head信息。它不显示在HTML网页正文里，显示在浏览器窗口的标题栏里。见图：

![头部信息(head)中的标题(title)](http://www.admin5.com/html/images/html_tutorials/head_title.gif)

示例代码如下：

    
    <head><title>HTML中文教程头部信息(head)之标题(title)说明</title></head>




## 链接(link)


用链接(link)可以建立和外部文件的链接。常用的是对CSS外部样式表(external style sheet)的链接。示例代码如下：

    
    <link rel="stylesheet" href="mainstyles.css" type="text/css">


有关CSS外部样式表和示例，[详见CSS简介](http://www.admin5.com/html/css_tutorials/001_CSS_Overview.html)。


## 样式(style)


用样式(style)可以设值网页的内部样式表(internal style sheet)。示例代码如下：

    
    <head>



    
    <style>



    
       body {background-color:white; color:black;}



    
       h1 {font: 18pt arial bold;}



    
    </style>



    
    </head>


有关CSS内部样式表和示例，[详见CSS简介](http://www.admin5.com/html/css_tutorials/001_CSS_Overview.html)。


##  关于网页信息(meta)


在计算机语言里，你经常可以看到一个前缀 -- meta，meta就是“关于”(about)的意思。

这meta解释起来比较拗口，比如metadata，意为描述data的data，英文即data about data。还有一个词叫metalanguage，表示一种描述其它语言的语言。再举一个例子，metafile，表示描述其它文件的文件。

在HTML里，meta标记(meta tags)表示用来描述网页的有关信息。示例代码如下：

    
    <meta name="description" content="HTML中文教程之头部信息">



    
    <meta name="keywords" content="HTML,tutorials,source codes">



    
    <meta name="author" content="编点网">




利用meta中的Refresh你还可以实现自动跳转页面的功能。示例代码：

    
    <meta http-equiv="Refresh" content="5;url=http://www.codesth.com/html/html_tutorials/index.html">


[演示示例](http://www.admin5.com/html/html_examples/063_meta_refresh.html)
