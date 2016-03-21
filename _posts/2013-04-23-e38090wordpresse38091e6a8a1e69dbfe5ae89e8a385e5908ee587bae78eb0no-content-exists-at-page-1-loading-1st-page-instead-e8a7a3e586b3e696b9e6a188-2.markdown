---
author: xjh1994
comments: true
date: 2013-04-23 13:27:39+00:00
layout: post
slug: '%e3%80%90wordpress%e3%80%91%e6%a8%a1%e6%9d%bf%e5%ae%89%e8%a3%85%e5%90%8e%e5%87%ba%e7%8e%b0no-content-exists-at-page-1-loading-1st-page-instead-%e8%a7%a3%e5%86%b3%e6%96%b9%e6%a1%88-2'
title: 【WordPress】模板安装后出现"No content exists at page 1! Loading 1st page instead."解决方案
wordpress_id: 462
categories:
- 未分类
---

主要有以下几种可能：

1.可能是function.php里写了条件，首页显示page1。 可以试试在主题自定义里修改首页为指定页面；

2.也可能是你设置了目录为首页，但网站没有页面。看看是不是你忘了保存设置了？

3.Open the file "glide.php" template, look at the line 8 => "selected: 1" and replace the value of 1 for 0.

如果网站模板存在glide.php，找到该文件第8行，将"selected: 1"中的“1”改为“0”；

4.网站还没有内容，新建些内容试试；

**5.主题不兼容，看看主题说明文件;**

6.将css文件中以下部分内容改为

[css]<div class='glidecontentwrapper' id='glidercontent'>
<div class='widget-content'>
<div class='glidecontenttoggler' id='togglebox'>
<a class='prev' href='#'></a>
<a class='next' href='#'></a>
</div>[/css]



[css]<div class='glidecontentwrapper' id='glidercontent'>

<div class='glidecontent'>
Hi
</div>
<div class='glidecontent'>
There
</div>
<div class='glidecontent'>
Folks
</div>

</div>
<div class='glidecontenttoggler' id='togglebox'>
<a class='prev' href='#'></a>
<a class='next' href='#'></a>
</div>[/css]
