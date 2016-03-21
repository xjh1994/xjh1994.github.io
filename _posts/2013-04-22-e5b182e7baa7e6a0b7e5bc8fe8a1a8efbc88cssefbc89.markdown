---
author: xjh1994
comments: true
date: 2013-04-22 10:39:24+00:00
layout: post
slug: '%e5%b1%82%e7%ba%a7%e6%a0%b7%e5%bc%8f%e8%a1%a8%ef%bc%88css%ef%bc%89'
title: 层级样式表（CSS）
wordpress_id: 51
categories:
- HTML&amp;CSS
tags:
- CSS
- 层级样式表
---

W3C  CSS验证服务：[http://jigsaw.w3.org/css-validator/](http://jigsaw.w3.org/css-validator/)

级联样式表（Cascading Style Sheet）简称“CSS”，通常又称为“风格样式表（Style Sheet）”，它是用来进行网页风格设计的。比如，如果想让链接字未点击时是蓝色的，当鼠标移上去后字变成红色的且有下划线，这就是一种风格。通过设立样式表，可以统一地控制HTML中各标志的显示属性。级联样式表可以使人更能有效地控制网页外观。使用级联样式表，可以扩充精确指定网页元素位置，外观以及创建特殊效果的能力。


          CSS是[英语](http://baike.baidu.com/view/1458.htm)Cascading Style Sheets（层叠样式表单）的缩写，它是一种用来表现[HTML](http://baike.baidu.com/view/692.htm)或[XML](http://baike.baidu.com/view/63.htm)等文件样式的计算机语言。




CSS目前最新版本为[CSS3](http://baike.baidu.com/view/1713027.htm)，是能够真正做到[网页](http://baike.baidu.com/view/828.htm)表现与内容分离的一种样式设计语言。相对于传统HTML的表现而言，CSS能够对网页中的[对象](http://baike.baidu.com/view/2387.htm)的位置排版进行[像素](http://baike.baidu.com/view/575.htm)级的精确控制，支持几乎所有的字体字号样式，拥有对网页对象和模型样式编辑的能力，并能够进行初步[交互设计](http://baike.baidu.com/view/426920.htm)，是目前基于文本展示最优秀的表现设计语言。CSS能够根据不同使用者的理解能力，简化或者优化写法，针对各类人群，有较强的易读性。







## 发展历史




**CSS1**




作为一项 W3C 推荐，[CSS1](http://baike.baidu.com/view/4232435.htm)发布于 1996 年 12 月 17 日。1999 年 1 月 11 日，此推荐被重新修订。[1]




**CSS2**




作为一项 W3C 推荐，[CSS2](http://baike.baidu.com/view/1664073.htm)发布于 1999 年 1 月 11 日。CSS2 添加了对媒介（打印机和听觉设备）和可下载字体的支持。[2]




**CSS3**




CSS3 计划将 CSS 划分为更小的模块。




**W3C CSS 规范和时间线**


<table >
<tbody >
<tr >



规范





草案/提议





推荐


</tr>
<tr >

<td >


CSS 1

</td>

<td >
</td>

<td >


1996 年 12 月 17 日

</td>
</tr>
<tr >

<td >


CSS 1 (Revised)

</td>

<td >
</td>

<td >


1999 年 1 月 11 日

</td>
</tr>
<tr >

<td >


CSS 2

</td>

<td >
</td>

<td >


1998 年 5 月 12 日

</td>
</tr>
<tr >

<td >


CSS 2.1

</td>

<td >


2007 年 7 月 19 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 2 Mobile

</td>

<td >


2007 年 10 月 19 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 2 TV

</td>

<td >


2003 年 5 月 14 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 2 Print

</td>

<td >


2006 年 10 月 13 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3

</td>

<td >


2001 年 5 月 23 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Namespace

</td>

<td >


2006 年 8 月 28 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 User Interface

</td>

<td >


2004 年 5 月 11 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Selectors

</td>

<td >


2005 年 12 月 15 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Fonts

</td>

<td >


2002 年 8 月 2 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Web Fonts

</td>

<td >


2002 年 8 月 2 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Colors

</td>

<td >


2003 年 5 月 14 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 TV

</td>

<td >


2003 年 5 月 14 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Backgrounds and borders

</td>

<td >


2005 年 2 月 16 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Text

</td>

<td >


2007 年 3 月 6 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Lists

</td>

<td >


2002 年 11 月 7 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Line

</td>

<td >


2002 年 5 月 15 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Box model

</td>

<td >


2007 年 8 月 9 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Multi column

</td>

<td >


2007 年 6 月 6 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Ruby

</td>

<td >


2003 年 5 月 14 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Border

</td>

<td >


2005 年 3 月 16 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Speech

</td>

<td >


2004 年 12 月 16 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Paged Media (PM)

</td>

<td >


2006 年 10 月 10 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Generated PM

</td>

<td >


2007 年 5 月 4 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Print

</td>

<td >


2006 年 10 月 13 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Values

</td>

<td >


2006 年 9 月 19 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Cascade

</td>

<td >


2005 年 12 月 15 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Template Layout

</td>

<td >


2009 年 4 月 2 日

</td>

<td >
</td>
</tr>
<tr >

<td >


CSS 3 Media Queries

</td>

<td >


2009 年 9 月 15 日

</td>

<td >
</td>
</tr>
</tbody>
</table>


## 使用方法




有三种方法可以在站点网页上使用样式表：




外部样式：将网页链接到外部样式表。




内页样式：在网页上创建嵌入的样式表。




行内样式：应用内嵌样式到各个网页元素。




每一种方法均有其优缺点：




当要在站点上所有或部分网页上一致地应用相同样式时，可使用外部样式表。在一个或多个外部样式表中定义样式，并将它们[链接](http://baike.baidu.com/view/147669.htm)到所有网页，便能确保所有网页外观的一致性。如果人们决定更改样式，只需在外部样式表中修改一次，而该更改会反映到所有与该样式表相链接的网页上。通常外部样式表以 .css 做为文件扩展名，例如 Mystyles.css。然后在需要此样式的页面中将其链接进来，如：




<link href="/css/Mystyles.css" rel="stylesheet" type="text/css"/>




当人们只是要定义当前网页的样式，可使用嵌入的样式表。嵌入的样式表是一种级联样式表，“嵌”在网页的 <HEAD> 标记符内。嵌入的样式表中的样式只能在同一网页上使用。 如：




<style type="text/css">




<!-- /* 把声明的样式包含在一个html注释中，这样可以解决较老的浏览器不识别style的问题 */




body {background:grey;}




-->




</style>




使用内嵌样式以应用级联样式表属性到网页元素上。 如：




<pstyle="@import url('style3.css');">CSS document</p><!-- 不能在style属性中使用@import -->




如果网页链接到外部样式表，为网页所创建的内嵌的或嵌入式样式将扩充或覆盖外部样式表中的指定属性。




要在网页上使用外部样式表的样式，可将该网页链接到样式表，方法是使用位于 “格式” 菜单上的 “样式表连接” 命令。可以链接一个或数个样式表到网页视图模式下的当前网页，或到在文件夹列表中的所选网页，或到站点上的全部网页。




该“样式” 框列出标准 HTML 标记符，例如标题




1，还有嵌入的样式表或链接到网页的外部样式表中所含的类或 ID 选择器。要应用样式到网页元素，请选定该样式然后单击 “样式” 框中的样式或选择器。




在 Microsoft FrontPage 2000 中，某些格式设置特性会作为内嵌样式自动应用。例如∶如果使用 “边框与阴影” 命令（在 “格式” 菜单上）在普通段落周围应用框，FrontPage 会写下格式设置信息，作为段落标记符的内嵌样式属性（例如∶ <p style="border-style: solid">）。然而某些属性的应用需要使用 CSS，其他则需要使用 HTML 。如果人们只想使用 CSS 应用内嵌样式，可使用 “样式” 按钮（位于网页元素的 “属性” 对话框里）应用类或 ID 选择器或嵌入式样式。




## 布局特点




对于[蜘蛛](http://baike.baidu.com/view/8483.htm)在爬行一个网站的页面时，若是有太多的垃圾代码，会使搜索蜘蛛对其产生不友好、不信任感，同时蜘蛛的爬行速度也会因此而减缓，对于网站[SEO](http://baike.baidu.com/view/1047.htm)而言，可谓一大忌。就如传统的用table页面，对此我们就需要对网站进行[代码优化](http://baike.baidu.com/view/2136208.htm)，而这便需要动用CSS+div了，下面便来谈谈使用CSS+div进行代码优化的一些益处。




一.精简代码，建设重构难度。




网站使用[DIV+CSS](http://baike.baidu.com/view/399288.htm)布局使代码很是精简，相信大多朋友也都略有所闻，css文件可以在网站的任意一个页面进行调用，而若是使用table表格修改部分页面却是显得很麻烦。要是一个[门户网站](http://baike.baidu.com/view/9803.htm)的话，需手动改很多页面，而且看着那些表格也会感觉很乱也很浪费时间，但是使用css+div布局只需修改css文件中的一个代码即可。




二.网页访问速度




使用了DIV+CSS布局的网页与[Table](http://baike.baidu.com/view/606543.htm)布局比较，精简了许多页面代码，那么其浏览访问速度自然得以提升，也从而提升了网站的[用户体验度](http://baike.baidu.com/view/8117932.htm)。




三.SEO优化




采用div-css布局的网站对于搜索引擎很是友好，因此其避免了Table嵌套层次过多而无法被[搜索引擎](http://baike.baidu.com/view/1154.htm)抓取的问题，而且简洁、结构化的代码更加有利于突出重点和适合搜索引擎抓取。




四.浏览器兼容性




DIV+CSS相比TABLE布局，更容易出现多种浏览器不兼容的问题，主要原因是不同的浏览器对web标准默认值不同。国内主流是ie，firefox及chrome用的较少，在兼容性测试方面，首先需要保证在ie多版本不出现问题，这里涉及到一些方法和技巧，可以针对具体问题在网站查找解决办法。




五.[CSS](http://baike.baidu.com/view/15916.htm)+DIV[网页](http://baike.baidu.com/view/828.htm)布局的时候常犯的小[错误](http://baike.baidu.com/view/120927.htm)




1. 检查[HTML](http://baike.baidu.com/view/692.htm)元素是否有拼写[错误](http://baike.baidu.com/view/120927.htm)、是否忘记结束标记




即使是老手也经常会弄错div的嵌套关系。可以用[dreamweaver](http://baike.baidu.com/view/7919.htm)的验证功能检查一下有无错误。




2. 检查CSS是否书写正确




检查一下有无拼写[错误](http://baike.baidu.com/view/120927.htm)、是否忘记结尾的 } 等。可以利用[CleanCSS](http://baike.baidu.com/view/4922294.htm)来检查 CSS的拼写错误。CleanCSS本是为CSS[减肥](http://baike.baidu.com/view/3976.htm)的[工具](http://baike.baidu.com/view/74746.htm)，但也能检查出拼写错误。




3. 用删除法确定错误发生的位置




如果错误影响了整体布局，则可以逐个删除[div](http://baike.baidu.com/view/26140.htm)块，直到删除某个div块后显示恢复正常，即可确定错误发生的位置。




4. 利用border[属性](http://baike.baidu.com/view/77730.htm)确定出错元素的[布局](http://baike.baidu.com/view/215902.htm)特性




使用float属性布局一不小心就会出错。这时为元素添加border属性确定元素边界，错误原因即水落石出。




5. float元素的父元素不能指定clear[属性](http://baike.baidu.com/view/77730.htm)




MacIE[3]下如果对float的元素的父元素使用clear[属性](http://baike.baidu.com/view/77730.htm)，周围的float元素布局就会混乱。这是MacIE的著名的bug，倘若不知道就会走弯路。




6. float元素务必指定width属性




很多[浏览器](http://baike.baidu.com/view/7718.htm)在显示未指定width的float元素时会有bug。所以不管float元素的内容如何，一定要为其指定width属性。




另外指定元素时尽量使用em而不是px做单位。




7. float元素不能指定margin和padding等属性




IE在显示指定了margin和padding的float元素时有bug。因此不要对float元素指定margin和padding属性(可以在float元素内部嵌套一个div来设置margin和padding)。也可以使用hack方法为IE指定特别的值。




8. float元素的宽度之和要小于100%




如果float[元素](http://baike.baidu.com/view/19993.htm)的宽度之和正好是100%，某些古老的[浏览器](http://baike.baidu.com/view/7718.htm)将不能正常显示。因此请保证宽度之和小于99%。




9. 是否重设了默认的样式?




某些属性如margin、padding等，不同[浏览器](http://baike.baidu.com/view/7718.htm)会有不同的[解释](http://baike.baidu.com/view/125857.htm)。因此最好在开发前首先将全体的margin、padding设置为0、列表样式设置为none等。




10. 是否忘记了写DTD?




如果无论怎样调整不同浏览器显示结果还是不一样，那么可以检查一下页面开头是不是忘了写下DTD声明。




最后，需要注意的是，蜘蛛不喜欢一个页面有太多的css代码，否则同样会影响蜘蛛的爬行，影响搜索引擎的收录，所以采用外部调用的方式调用CSS是非常不错的方法。而同时，若非必须太多花哨的网站，采用CSS布局，同样可以到达所想要的效果。如[网站导航](http://baike.baidu.com/view/678522.htm)中的文字颜色变化、[下拉菜单](http://baike.baidu.com/view/1143846.htm)等。




## 创建编辑




创建和编辑css更加常用的是[Adobe](http://baike.baidu.com/view/7578.htm)[Dreamweaver](http://baike.baidu.com/view/7919.htm)系列软件，可视化编辑更利于web工程师快速的创建和编辑css，新版本CS5.0、CS5.5、CS6，包含Adobe BrowserLab，用于针对多种浏览器测试css的兼容性。Adobe Dreamweaver是一个css创建和编辑必不可少的利器！




[FrontPage](http://baike.baidu.com/view/118446.htm)2000 包含有能用来为站点创建外部样式表的模板。可以用空白模板或已包含样式的模板来创建（例如 Arcs）。当保存样式表时， FrontPage 会以 . css 作为文件扩展名。要编辑样式表，请双击文件夹列表中的样式表。




当创建或修改网页样式时，可使用位于 “格式” 菜单的 “样式” 命令，FrontPage 会自动创建嵌入的样式表（如果原先不存在），并在嵌入的样式表内将此样式保存为类选择器。




可以使用 “样式” 对话框来创建新类选择器，修改或删除现有类选择器，或将 CSS 格式设置属性应用到标准[HTML](http://baike.baidu.com/view/692.htm)标记符上例如 <H1>。当单击 “确定” 关闭对话框时，FrontPage 会将格式设置特征写回到使用正确语法的外部或嵌入的样式表中。或者，可以用正确 CSS 语法键入样式信息。要键入嵌入的样式表的样式信息，请单击网页视图模式下的 “HTML” 选项卡。




如果对应用到站点的主题选择 “应用 CSS ” 复选框，FrontPage 将在站点的根目录下创建名为 Theme 1 .css 的文件，其中 Theme 是主题的名称。如果修改主题，FrontPage 自动将更改写回主题 CSS 里。也可以通过直接编辑主题 CSS 来修改主题。




## 删除样式




在页面视图下打开样式文件，格式/样式命令，从打开的“样式”对话框中选择要删除的样式，单击“删除”。







来自百度百科



