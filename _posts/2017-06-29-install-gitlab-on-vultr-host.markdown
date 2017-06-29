---
author: xjh1994
comments: true
date: 2017/6/29 10:32:27
layout: post
slug: gitlab vultr
title: 在Vultr主机上安装GitLab报502错误
categories:
- GitLab
- Vultr
tag:
- GitLab
- Vultr
---

在Vultr的单核1G主机上安装GitLab，访问时出现 `502 ，Whoops, GitLab is taking too much time to respond` 错误，已排除端口问题，最终在GitLab官网的 `Requirements` 里看到安装要求，1G内存的需要3GSwap空间，于是尝试了一下，最后成功了。

创建Swap空间的过程中也遇到了几个问题，记录一下：

- 使用 `sudo dd if=/dev/zero of=/swapfile bs=1G count=4` 命令创建空间时报错：`dd: memory exhausted by input buffer of size 1073741...`

  解决：改用 `sudo dd if=/dev/zero of=/swapspace bs=1M count=4000
`

- 创建完空间启用时，执行命令 `swapon swapfile`，报错 `insecure permissions 0644, 0600 suggested.` 以及 `read swap header failed : Invalid argument`

  解决：先给swapfile赋予 `600` 或者 `644` 权限： `chmod 600 swapfile` ，然后使用 `mkswap` 将文件格式化成swap格式： `mkswap swapfile`，接着再执行 `swapon` 命令即可成功激活swap空间
