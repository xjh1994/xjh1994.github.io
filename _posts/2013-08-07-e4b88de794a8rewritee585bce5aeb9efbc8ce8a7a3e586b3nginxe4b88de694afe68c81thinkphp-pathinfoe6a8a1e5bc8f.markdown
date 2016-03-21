---
author: xjh1994
comments: true
date: 2013-08-07 03:07:47+00:00
layout: post
slug: '%e4%b8%8d%e7%94%a8rewrite%e5%85%bc%e5%ae%b9%ef%bc%8c%e8%a7%a3%e5%86%b3nginx%e4%b8%8d%e6%94%af%e6%8c%81thinkphp-pathinfo%e6%a8%a1%e5%bc%8f'
title: 不用rewrite/兼容，解决Nginx不支持ThinkPHP pathinfo模式
wordpress_id: 478
categories:
- 未分类
---


修改nginx.conf,找到server中的 location ~ .php${},修改为location ~ .php {},并增加以下内容：

`set $path_info "";
set $real_script_name $fastcgi_script_name;
if ($fastcgi_script_name ~ "^(.+?.php)(/.+)$") {
set $real_script_name $1;
set $path_info $2;
}
fastcgi_param SCRIPT_FILENAME $document_root$real_script_name;
fastcgi_param SCRIPT_NAME $real_script_name;
fastcgi_param PATH_INFO $path_info;`

如果仍未解决，在ThinkPHP入口文件index.php中加入配置define('_PHP_FILE_',$_SERVER['SCRIPT_NAME']);
