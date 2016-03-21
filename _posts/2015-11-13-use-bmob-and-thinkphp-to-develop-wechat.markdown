---
author: xjh1994
comments: true
date: 2015-11-13 15:20:21+00:00
layout: post
slug: use-bmob-and-thinkphp-to-develop-wechat
title: 使用Bmob+ThinkPHP三步开发微信公众账号教程
wordpress_id: 570
categories:
- ThinkPHP
- 原创
- 安卓
- 开源项目
tags:
- Bmob
- ThinkPHP
- Wechat
- 公众号
- 微信
- 教程
---

最近需要开发一个微信公众号，服务端用的是[Bmob](http://www.bmob.cn/)，Bmob也提供了云端代码开发微信，但只能使用JS语法，不够灵活 。于是准备用PHP来开发。ThinkPHP是国内最普及的PHP开发框架。（没有使用过的朋友可以去[官网](http://www.thinkphp.cn/)了解一下，上手很快）

ThinkPHP的使用者还为微信公众号开发了配套的SDK，使用很方便，例如只需调用$wechat->reply("回复内容");即可回复公众号信息。

闲话不多说，接下来我们看一下怎么用ThinkPHP三步开发微信公众账号。


# 所需下载文件：





	
  1. **[微信ThinkPHP开发包](http://www.thinkphp.cn/extend/673.html) ** 这是ThinkPHP网友开发的微信扩展包，不光可以用ThinkPHP开发，只要是PHP都可以。Github地址：[https://github.com/gaoming13/wechat-php-sdk](https://github.com/gaoming13/wechat-php-sdk)




## 已完成的功能模块




Wechat （处理自动接入、获取与回复微信消息）([使用说明](https://github.com/xjh1994/wechat-php-sdk-2#wechat-%E6%A8%A1%E5%9D%97%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E))






	
  * [接收普通消息/事件推送](https://github.com/xjh1994/wechat-php-sdk-2#wechat-%E6%8E%A5%E6%94%B6%E6%99%AE%E9%80%9A%E6%B6%88%E6%81%AF%E4%BA%8B%E4%BB%B6%E6%8E%A8%E9%80%81)

	
  * [被动回复（文本、图片、语音、视频、音乐、图文）](https://github.com/xjh1994/wechat-php-sdk-2#wechat-%E8%A2%AB%E5%8A%A8%E5%9B%9E%E5%A4%8D%E6%96%87%E6%9C%AC%E5%9B%BE%E7%89%87%E8%AF%AD%E9%9F%B3%E8%A7%86%E9%A2%91%E9%9F%B3%E4%B9%90%E5%9B%BE%E6%96%87)

	
  * [转发到多客服接口](https://github.com/xjh1994/wechat-php-sdk-2#wechat-%E8%BD%AC%E5%8F%91%E5%88%B0%E5%A4%9A%E5%AE%A2%E6%9C%8D%E6%8E%A5%E5%8F%A3)




Api （处理需要access_token的主动接口）([使用说明](https://github.com/xjh1994/wechat-php-sdk-2#api-%E6%A8%A1%E5%9D%97%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E))






	
  * [主送发送客服消息（文本、图片、语音、视频、音乐、图文）](https://github.com/xjh1994/wechat-php-sdk-2#api%E5%8F%91%E9%80%81%E5%AE%A2%E6%9C%8D%E6%B6%88%E6%81%AF%E6%96%87%E6%9C%AC%E5%9B%BE%E7%89%87%E8%AF%AD%E9%9F%B3%E8%A7%86%E9%A2%91%E9%9F%B3%E4%B9%90%E5%9B%BE%E6%96%87)

	
  * [多客服功能（客服管理、多客服回话控制、获取客服聊天记录等）](https://github.com/xjh1994/wechat-php-sdk-2#api%E5%A4%9A%E5%AE%A2%E6%9C%8D%E5%8A%9F%E8%83%BD%E5%AE%A2%E6%9C%8D%E7%AE%A1%E7%90%86%E5%A4%9A%E5%AE%A2%E6%9C%8D%E5%9B%9E%E8%AF%9D%E6%8E%A7%E5%88%B6%E8%8E%B7%E5%8F%96%E5%AE%A2%E6%9C%8D%E8%81%8A%E5%A4%A9%E8%AE%B0%E5%BD%95%E7%AD%89)

	
  * [素材管理（临时素材、永久素材、素材统计）](https://github.com/xjh1994/wechat-php-sdk-2#api%E7%B4%A0%E6%9D%90%E7%AE%A1%E7%90%86%E4%B8%B4%E6%97%B6%E7%B4%A0%E6%9D%90%E6%B0%B8%E4%B9%85%E7%B4%A0%E6%9D%90%E7%B4%A0%E6%9D%90%E7%BB%9F%E8%AE%A1)

	
  * [自定义菜单管理（创建、查询、删除菜单）](https://github.com/xjh1994/wechat-php-sdk-2#api%E8%87%AA%E5%AE%9A%E4%B9%89%E8%8F%9C%E5%8D%95%E7%AE%A1%E7%90%86%E5%88%9B%E5%BB%BA%E6%9F%A5%E8%AF%A2%E5%88%A0%E9%99%A4%E8%8F%9C%E5%8D%95)

	
  * [微信JSSDK（生成微信JSSDK所需的配置信息）](https://github.com/xjh1994/wechat-php-sdk-2#api%E5%BE%AE%E4%BF%A1jssdk%E7%94%9F%E6%88%90%E5%BE%AE%E4%BF%A1jssdk%E6%89%80%E9%9C%80%E7%9A%84%E9%85%8D%E7%BD%AE%E4%BF%A1%E6%81%AF)

	
  * [账号管理（生成带参数的二维码、长链接转短链接接口）](https://github.com/xjh1994/wechat-php-sdk-2#api%E8%B4%A6%E5%8F%B7%E7%AE%A1%E7%90%86%E7%94%9F%E6%88%90%E5%B8%A6%E5%8F%82%E6%95%B0%E7%9A%84%E4%BA%8C%E7%BB%B4%E7%A0%81%E9%95%BF%E9%93%BE%E6%8E%A5%E8%BD%AC%E7%9F%AD%E9%93%BE%E6%8E%A5%E6%8E%A5%E5%8F%A3)

	
  * [用户管理（用户分组管理、设置用户备注名、获取用户基本信息、获取用户列表、网页授权获取用户基本信息）](https://github.com/xjh1994/wechat-php-sdk-2#api%E7%94%A8%E6%88%B7%E7%AE%A1%E7%90%86%E7%94%A8%E6%88%B7%E5%88%86%E7%BB%84%E7%AE%A1%E7%90%86%E8%AE%BE%E7%BD%AE%E7%94%A8%E6%88%B7%E5%A4%87%E6%B3%A8%E5%90%8D%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E5%9F%BA%E6%9C%AC%E4%BF%A1%E6%81%AF%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E5%88%97%E8%A1%A8%E7%BD%91%E9%A1%B5%E6%8E%88%E6%9D%83%E8%8E%B7%E5%8F%96%E7%94%A8%E6%88%B7%E5%9F%BA%E6%9C%AC%E4%BF%A1%E6%81%AF)

	
  * 数据统计接口（开发中...）


2. ** [ThinkPHP完整包](http://www.thinkphp.cn/)**

3. ** [Bmob PHP SDK](https://github.com/bmob/bmob-php-sdk/archive/master.zip) **（只需要其中的lib目录下文件） [Github地址](https://github.com/bmob/bmob-php-sdk)


# **开发步骤**：（以下有必要ThinkPHP简称TP）




#### **一：**将wechat-php-sdk内 src 文件夹重命名为 Gaoming13, 拷贝至 ThinkPHP/Library/ 下。（文件内有Gaoming13命名空间，可以自行修改，建议不要修改，尊重作者劳动成果）




#### 二：在TP默认的IndexController中调用以下代码，具体appid等值需自行配置。（详细代码件wechat-php-sdk/demo/demo_thinkPHP.php文件）



    
    
    // 开发者中心-配置项-AppID(应用ID)
    $appId = 'wx733d7f24bd29224a';
    // 开发者中心-配置项-AppSecret(应用密钥)
    $appSecret = 'c6d165c5785226806f42440e376a410e';
    // 开发者中心-配置项-服务器配置-Token(令牌)
    $token = 'gaoming13';
    // 开发者中心-配置项-服务器配置-EncodingAESKey(消息加解密密钥)
    $encodingAESKey = '072vHYArTp33eFwznlSvTRvuyOTe5YME1vxSoyZbzaV';
    
    // wechat模块 - 处理用户发送的消息和回复消息
    $wechat = new \Gaoming13\WechatPhpSdk\Wechat(array(
    'appId' => $appId,
    'token' => $token,
    'encodingAESKey' => $encodingAESKey //可选
    ));
    // api模块 - 包含各种系统主动发起的功能
    $api = new \Gaoming13\WechatPhpSdk\Api(
    array(
    'appId' => $appId,
    'appSecret' => $appSecret,
    'get_access_token' => function(){
    // 用户需要自己实现access_token的返回
    return S('wechat_token');
    },
    'save_access_token' => function($token) {
    // 用户需要自己实现access_token的保存
    S('wechat_token', $token);
    }
    )
    );
    
    // 获取微信消息
    $msg = $wechat->serve();
    
    // 回复文本消息
    if ($msg->MsgType == 'text' && $msg->Content == '你好') {
    $wechat->reply("你也好！ - 这是我回复的额！");
    } else {
    $wechat->reply("听不懂！ - 这是我回复的额！");
    }
    
    // 主动发送
    $api->send($msg->FromUserName, '这是我主动发送的一条消息');
    




### 三、使用Bmob PHPSDK




#### 将下载好的SDK下lib目录修改为Bmob，然后复制到ThinkPHP/Library/ 下，并且将里面的每个.class.php文件前加上命名空间：namespace Bmob;（这是TP3.2的要求，之前的版本可忽略此修改）[不想麻烦的同学点这里下载](http://pan.baidu.com/s/1jG3zO8Y)修改好的文件


修改BmobConfig.class.php，填写AppID和SecretKey信息。如下：


    
    
    class BmobConfig{
    const APPID = ''; //替换后台"应用密钥"中的Application ID
    const RESTKEY = ''; //后台"应用密钥"中的REST API Key
    const BMOBURL = 'https://api.bmob.cn/1/'; //保持不变
    }
    



注意在TP的Controller中调用时要加命名空间信息：

    
    
    use Bmob\BmobUser;
    use Bmob\BmobObject;
    


然后通过以下代码获取数据，再用上一步的方法返回给微信用户即可。

$bmobObj =newBmobObject("GameScore");

$res=$bmobObj->get();// 获取所有GameScore对象

具体操作Bmob数据方法见[Bmob官方文档](http://docs.bmob.cn/phpsdk/index.html?menukey=otherdoc&key=phpsdk#index_类库说明)



注意点：

中文可能会出现乱码，在Controller construct方法中加入
    
    header("content-type:text/html;charset=utf-8");

即可
