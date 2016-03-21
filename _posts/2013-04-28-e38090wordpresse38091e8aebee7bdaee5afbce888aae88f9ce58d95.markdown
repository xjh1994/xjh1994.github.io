---
author: xjh1994
comments: true
date: 2013-04-28 15:49:12+00:00
layout: post
slug: '%e3%80%90wordpress%e3%80%91%e8%ae%be%e7%bd%ae%e5%af%bc%e8%88%aa%e8%8f%9c%e5%8d%95'
title: 【WordPress】设置导航菜单
wordpress_id: 139
categories:
- WordPress
tags:
- WordPress
- 导航
---

### 如何确定主题是否支持自定义菜单功能？


启用主题后，访问后台 - 外观 - 菜单，如果你看到下图所示内容，说明主题不支持自定义菜单，反之，则支持：

![wpdaxue.com-201303417](http://img.wpdaxue.com/2013/03/wpdaxue.com-201303417.png)


### 自定义导航菜单


在自定义菜单之前，你需要创建好所需的文章分类和页面，请参考《[创建和管理文章分类](http://www.wpdaxue.com/create-wordpress-categories.html)》，下面进入正题。


#### 创建菜单


打开后台 - 外观 - 菜单，然后点击页面上的“+”按钮，填写一个菜单的名字（可以是任意文字，只是用来识别罢了），然后点击“创建菜单”。比如下图我创建一个名为“菜单”的菜单：

![wpdaxue.com-201303415](http://img.wpdaxue.com/2013/03/wpdaxue.com-201303415.png)


<blockquote>注：有些新手朋友误以为这里添加的“菜单”就是一个单独的链接，其实不是这样的，这个“菜单”是一组链接，你可以给他添加N个链接，组成导航条。</blockquote>




#### 添加链接和设置菜单


![wpdaxue.com-201303416](http://img.wpdaxue.com/2013/03/wpdaxue.com-201303416.png)

①从左边选择需要添加的链接（自定义链接、页面链接和分类链接），加入到菜单中去。（自定义链接：允许你添加任何链接，比如你可以添加一个首页，链接指向首页网址即可）

②可以编辑每个菜单项目的信息，并用拖放的方式为其排序。将某个菜单项稍稍向右拖动，这个项目即变为子菜单（低一格就是二级菜单，低两格就是三级菜单，以此类推。前提是你的WordPress主题支持显示子菜单哦），这样您的菜单便有了层级关系。

③排好菜单以后，点击“保存菜单”。

④然后为你设置的菜单选择显示的位置（有些WordPress主题支持不同位置调用不同菜单，所以你可以设置不同的菜单，然后选择显示位置）。


#### 菜单高级设置


WordPress菜单隐藏了一些功能，如果你想控制菜单更多的属性，不妨点击屏幕右上角的“显示选项”，让隐藏的功能都显示出来：

![wpdaxue.com-201303419](http://img.wpdaxue.com/2013/03/wpdaxue.com-201303419.png)

你可以选择更多的菜单项目种类（例如标签和文章），还可以显示菜单的高级属性（链接目标、CSS类、链接关系网、描述）

![wpdaxue.com-201303420](http://img.wpdaxue.com/2013/03/wpdaxue.com-201303420.png)



	
  * **导航标签** - 就是链接的文字

	
  * **标题属性** - 就是a标签的title属性值，比如上图填写”WP大学”

	
  * **CSS类** - 给某个菜单项添加class，通过css是这个菜单项与众不同，如上图我添加了“home-page”

	
  * **链接关系网** - 通过链接关系网（XFN）给菜单添加rel属性，例如不想搜索引擎跟随这个菜单，可以为其添加rel="nofllow"属性

	
  * **链接目标** - 控制菜单打开方式，在新窗口打开（target="_blank"）或在当前窗口打开（默认）。


以下代码就是根据上图的设置显示的效果：



<table >
<tbody >
<tr >

<td >

    
    1
    2
    3



</td>

<td >

    
    <li class="home-page">
    <a title="编点网" target="_blank" rel="nofollow" href="http://www.codesth.com">编点网</a>
    </li>



</td>
</tr>
</tbody>
</table>



转自[http://www.wpdaxue.com/wordpress-nav-menus.html](http://www.wpdaxue.com/wordpress-nav-menus.html)
