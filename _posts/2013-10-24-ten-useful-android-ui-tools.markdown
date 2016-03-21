---
author: xjh1994
comments: true
date: 2013-10-24 04:00:21+00:00
layout: post
slug: ten-useful-android-ui-tools
title: 10款实用Android UI工具
wordpress_id: 379
categories:
- IT资讯
- Java
- 创意
- 前端
- 安卓
- 手机
- 系统工具
- 软件应用
tags:
- Android
- UI
- 工具
- 手机
---

移动应用的UI就好像达摩克利斯之剑，一方面，一个视觉、交互、体验良好的UI可以加强应用在用户心中的形象和识别性，而另一方面，一个体验糟糕的UI设计不仅使用户无法沉浸在应用内，而且还会造成用户对该应用产生厌恶感。所以在应用如海的Andriod世界里，一个高质量的对于应用的推广有着举足轻重的作用。为此，本文为广大的移动应用开发者推荐10款轻巧使用的UI设计工具。

**1. [ActionBarSherlock](http://actionbarsherlock.com/)**

ActionBarSherlock是一个独立的Android设计库，可以让Android 2.x的系统也能使用ActionBar。此外，ActionBarSherlock还能够允许开发者只通过一个API，就可以方便地使用和设计ActionBar。ActionBarSherlock还可以自主判断选择并调用原生Action Bar还是扩展ActionBar。如果在Android 3.x以上使用ActionBarSherlock，它还会调用系统原生的ActionBar。

[![](http://cms.csdnimg.cn/article/201310/22/526631e7a0b8a_middle.jpg)](http://cms.csdnimg.cn/article/201310/22/526631e7a0b8a.jpg)

**2. [Nine Old Androids](http://nineoldandroids.com/)**

自Android 3.0以上的版本，SDK新增了一个android.animation包，里面的类都是跟动画效果实现相关的，通过Honeycomb API，能够实现非常复杂的动画效果。但如果开发者想在3.0以下的版本中也能使用到这套API，那么Nine Old Androids就会是你最好的选择，该API和Honeycomb API完全一样，只是改变了你使用com.nineoldandroids.XXX的入口。

![](http://cms.csdnimg.cn/article/201310/22/52663193632f4_middle.jpg)

该项目包含两个工程，一个是Library，即为动画效果的实现库，另一个则是Sample，是对如何使用该API的演示。开发者可以直接登陆Google Play下载安装Nine Old Androids Sample，查看演示。

**3. [Pull To Refresh](https://github.com/erikwt/PullToRefresh-ListView)**

Android系统为我们中提供了ListView控件，ListView能够为我们展现丰富的内容，有时候我们为了提升用户体检，需要更炫而且更好用户体验的效果。通过使用Pull To Refresh，我们就能够实现下拉列表即可刷新当前页面内容的效果。

[![](http://cms.csdnimg.cn/article/201310/22/5266337278d65_middle.jpg)](http://cms.csdnimg.cn/article/201310/22/5266337278d65.jpg)

**4. [Progress Wheel](http://dribbble.com/shots/772003-RE-Progress-Wheel)**

Progress Wheel是一款能够取代Android原生Indeterminate式可显示具体进度的滚动式进度条。效果图如下。

[![](http://cms.csdnimg.cn/article/201310/22/52663463d9787_middle.jpg)](http://cms.csdnimg.cn/article/201310/22/52663463d9787.jpg)

**5. [ViewPagerIndicator](http://viewpagerindicator.com/)**

View Pager Indicator是一款基于Patrik Akerfeldt的ViewFlow，兼容了ViewPager和ActionBarSherlock的Android分页指针小部件，可用于实现工作区的UI设计。此外，View Pager Indicator可以帮助开发者实现Android左右滑屏的同时,标签可以跟着移动，实现了各种风格的Indicator。

[![](http://cms.csdnimg.cn/article/201310/22/52663504650b3_middle.jpg)](http://cms.csdnimg.cn/article/201310/22/52663504650b3.jpg)

**6. [Android Universal Image Loader](https://github.com/dodola/Android-Universal-Image-Loader)**

Android-Universal-Image-Loader是一款为Android打造的开源UI组件，旨在为开发者者提供一个异步加载图像功能。

Android-Universal-Image-Loader能为开发者提供多线程图片加载，灵活更改ImageLoader的基本配置（最大线程数、缓存方式、图片显示等）；图片异步加载缓（内存缓存及本地缓存）存机制；对加载过程实现监听和事件处理；配置加载图片的显示选项，包括图片圆角处理和加载完成显示动画等功能。此外，ImageLoader库大量使用了面向接口设计，更加专注于对象所提供的服务或模块的职责。

[![](http://cms.csdnimg.cn/article/201310/22/5266359849bad_middle.jpg)](http://cms.csdnimg.cn/article/201310/22/5266359849bad.jpg)

**7.[ ColorPicker](https://github.com/attenzione/android-ColorPickerPreference)**

ColorPicker是Android平台的颜色拾取器， 可以通过手机摄像头获取图像，或从本地图库中获取图像，然后点击所感兴趣的颜色，就可以知道所选颜色的RGB、HEX、HSV值。

[![](http://cms.csdnimg.cn/article/201310/22/526638e7b13f3_middle.jpg)](http://cms.csdnimg.cn/article/201310/22/526638e7b13f3.jpg)

**8. [Segmented Radio Button](https://github.com/vinc3m1/android-segmentedradiobutton)**

Segmented Radio Button可以在Android设备上实现iOS设备上分段控制效果的UI工具。

[![](http://cms.csdnimg.cn/article/201310/23/5267393644db9_middle.jpg)](http://cms.csdnimg.cn/article/201310/23/5267393644db9.jpg)

**9. [PhotoView](https://github.com/chrisbanes/PhotoView)**

PhotoView是对Android ImageView的拓展，支持通过单点/多点触摸来进行图片缩放的智能控件。

[![](http://cms.csdnimg.cn/article/201310/22/52663a57b7c1a_middle.jpg)](http://cms.csdnimg.cn/article/201310/22/52663a57b7c1a.jpg)

**主要特性：**



	
  * 支持平滑滚动

	
  * 支持单点、多点触摸，即时缩放图片

	
  * 在ViewPager等滑动父控件下能够运行良好


**10. [Smart Image View](https://github.com/loopj/android-smart-image-view)**

SmartImageView是用来取代Android自带ImgageView组件，通过SmartImageView，使用者可以使用URL、电话薄等多种方式来加载图片，另外，SmartImageView支持异步加载图片，图片将会被缓存在内存内，从而方便二次提取。
