---
author: xjh1994
comments: true
date: 2013-10-30 11:37:24+00:00
layout: post
slug: qzone-magic-blog-code
title: QQ空间魔力日志源代码
wordpress_id: 380
categories:
- 创意
tags:
- QQ
- qzone
- 源代码
---

**主文件do.php**
[php]
<?php
$referer=$_SERVER['HTTP_REFERER'];
$ip=GetIP();
// $referer="http://user.qzone.qq.com/977135148/infocenter";
if(!strpos($referer,'infocenter')){//如果不是从个人中心进来
	header('Location: no.png');
	exit();
}
//截取QQ
$urlArr = explode('/',$referer);
$qq = $urlArr['3'];
//用户姓名
$username = getQQName($qq);
//信息位置
include 'ip/IpLocation.class.php';
$ipClass = new IpLocation('UTFWry.dat');
$area = $ipClass->getlocation($ip);
$place = str_replace('CZ88.NET','',$area['country'].$area['area']);
//在线状态
$QQState = getQQState($qq);
$ua = $_SERVER['HTTP_USER_AGENT'];

//开始绘图
// $im = imagecreatefrompng("400X300.png");
//创建图像
$im = imagecreatetruecolor(400, 300);
$color=imagecolorallocate($im,255,255,255);
//设置透明
//imagecolortransparent($im,$color);
imagefill($im,0,0,$color);
//设置颜色
$pink  = ImageColorAllocate($im, 0 , 0 ,0);
$red   = ImageColorAllocate($im, 255 , 0 ,0);
$zise  = ImageColorAllocate($im, 0 , 255 ,0);
$fontfile = "fonts/msyh.ttf";//雅黑字库
//打印qzone头像
$qqlogo = imagecreatefromjpeg('http://qlogo3.store.qq.com/qzone/'.$qq.'/'.$qq.'/50');
imagecopy( $im, $qqlogo, 20, 23, 0, 0, 50, 50 );
ImageDestroy($qqlogo);
//打印用户名
ImageTTFText($im, 14,0,80,40,$pink,$fontfile,'@'.$qq.' '.$username);
//打印ip信息
ImageTTFText($im, 14,0,80,70,$pink,$fontfile,''.$place);
//打印文章内容
$con = array();
include 'content.php';
$rand = rand(0,count($con)-1);
ImageTTFText($im, 9,0,20,95,$pink,$fontfile,$con[$rand]);	
ImageTTFText($im, 10,0,110,295,$red,$fontfile,'纯属娱乐 谁看显谁 biezhivip.com 研发');
//ImageTTFText($im, 10,0,260,295,$red,$fontfile,'你若安好，便是晴天');
Header("Content-type: image/gif");
Imagegif($im);
ImageDestroy($im);
exit();
//获取ip
function GetIP(){
	if (getenv("HTTP_CLIENT_IP") && strcasecmp(getenv("HTTP_CLIENT_IP"), "unknown")){
		$ip = getenv("HTTP_CLIENT_IP");
	}else if (getenv("HTTP_X_FORWARDED_FOR") && strcasecmp(getenv("HTTP_X_FORWARDED_FOR"), "unknown")){
		$ip = getenv("HTTP_X_FORWARDED_FOR");
	}else if (getenv("REMOTE_ADDR") && strcasecmp(getenv("REMOTE_ADDR"), "unknown")){
		$ip = getenv("REMOTE_ADDR");
	}else if (isset($_SERVER['REMOTE_ADDR']) && $_SERVER['REMOTE_ADDR'] && strcasecmp($_SERVER['REMOTE_ADDR'], "unknown")){
		$ip = $_SERVER['REMOTE_ADDR'];
	}else{
		$ip = "unknown";
	}	
	//bae 的ip要特殊处理
	if (strpos($ip,',')) {
		$ipArr = explode(',',$ip);
		$ip = $ipArr[0];
	}
	return($ip);
}
//获取QQ状态
function getQQState($qq){
	$url ='http://wpa.qq.com/pa?p=2:'.$qq.':41&r=' . time ();
	$headInfo = get_headers($url,1);
	$length = $headInfo['Content-Length'];
	if ($length==1243) {
		return true;
	}else {
		return false;
	}
}
//获取QQ昵称
function getQQNick($qq){
	$str = file_get_contents('http://r.qzone.qq.com/cgi-bin/user/cgi_personal_card?uin='.$qq);
	$pattern = '/'.preg_quote('"nickname":"','/').'(.*?)'.preg_quote('",','/').'/i';
	preg_match ( $pattern,$str, $result );
	return $result[1];
}
//获取QQ姓名
function getQQName($qq){
	//$qqArr = include 'friendArr.php';//预先设置的
	//$username = $qqArr[$qq];
	if (!$username) {
		$username = getQQNick($qq);
	}
	return $username;
}
?>
[/php]

完整文件下载http://pan.baidu.com/s/103p7c
提取码lnkp
