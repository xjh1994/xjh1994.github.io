---
author: xjh1994
comments: true
date: 2013-04-26 01:59:22+00:00
layout: post
slug: '%e3%80%90php%e3%80%91-header-content-type%e7%b1%bb%e5%9e%8b'
title: 【PHP】 header Content-Type类型
wordpress_id: 130
categories:
- PHP&amp;MySQL
- 编程
tags:
- Content-Type
- PHP
---

`<?php `


```$mimetypes` `= ``array``( `




```'ez'` `=&gt; ``'application/andrew-inset'``, `




```'hqx'` `=&gt; ``'application/mac-binhex40'``, `




```'cpt'` `=&gt; ``'application/mac-compactpro'``, `




```'doc'` `=&gt; ``'application/msword'``, `




```'bin'` `=&gt; ``'application/octet-stream'``, `




```'dms'` `=&gt; ``'application/octet-stream'``, `




```'lha'` `=&gt; ``'application/octet-stream'``, `




```'lzh'` `=&gt; ``'application/octet-stream'``, `




```'exe'` `=&gt; ``'application/octet-stream'``, `




```'class'` `=&gt; ``'application/octet-stream'``, `




```'so'` `=&gt; ``'application/octet-stream'``, `




```'dll'` `=&gt; ``'application/octet-stream'``, `




```'oda'` `=&gt; ``'application/oda'``, `




```'pdf'` `=&gt; ``'application/pdf'``, `




```'ai'` `=&gt; ``'application/postscript'``, `




```'eps'` `=&gt; ``'application/postscript'``, `




```'ps'` `=&gt; ``'application/postscript'``, `




```'smi'` `=&gt; ``'application/smil'``, `




```'smil'` `=&gt; ``'application/smil'``, `




```'mif'` `=&gt; ``'application/vnd.mif'``, `




```'xls'` `=&gt; ``'application/vnd.ms-excel'``, `




```'ppt'` `=&gt; ``'application/vnd.ms-powerpoint'``, `




```'wbxml'` `=&gt; ``'application/vnd.wap.wbxml'``, `




```'wmlc'` `=&gt; ``'application/vnd.wap.wmlc'``, `




```'wmlsc'` `=&gt; ``'application/vnd.wap.wmlscriptc'``, `




```'bcpio'` `=&gt; ``'application/x-bcpio'``, `




```'vcd'` `=&gt; ``'application/x-cdlink'``, `




```'pgn'` `=&gt; ``'application/x-chess-pgn'``, `




```'cpio'` `=&gt; ``'application/x-cpio'``, `




```'csh'` `=&gt; ``'application/x-csh'``, `




```'dcr'` `=&gt; ``'application/x-director'``, `




```'dir'` `=&gt; ``'application/x-director'``, `




```'dxr'` `=&gt; ``'application/x-director'``, `




```'dvi'` `=&gt; ``'application/x-dvi'``, `




```'spl'` `=&gt; ``'application/x-futuresplash'``, `




```'gtar'` `=&gt; ``'application/x-gtar'``, `




```'hdf'` `=&gt; ``'application/x-hdf'``, `




```'js'` `=&gt; ``'application/x-javascript'``, `




```'skp'` `=&gt; ``'application/x-koan'``, `




```'skd'` `=&gt; ``'application/x-koan'``, `




```'skt'` `=&gt; ``'application/x-koan'``, `




```'skm'` `=&gt; ``'application/x-koan'``, `




```'latex'` `=&gt; ``'application/x-latex'``, `




```'nc'` `=&gt; ``'application/x-netcdf'``, `




```'cdf'` `=&gt; ``'application/x-netcdf'``, `




```'sh'` `=&gt; ``'application/x-sh'``, `




```'shar'` `=&gt; ``'application/x-shar'``, `




```'swf'` `=&gt; ``'application/x-shockwave-flash'``, `




```'sit'` `=&gt; ``'application/x-stuffit'``, `




```'sv4cpio'` `=&gt; ``'application/x-sv4cpio'``, `




```'sv4crc'` `=&gt; ``'application/x-sv4crc'``, `




```'tar'` `=&gt; ``'application/x-tar'``, `




```'tcl'` `=&gt; ``'application/x-tcl'``, `




```'tex'` `=&gt; ``'application/x-tex'``, `




```'texinfo'` `=&gt; ``'application/x-texinfo'``, `




```'texi'` `=&gt; ``'application/x-texinfo'``, `




```'t'` `=&gt; ``'application/x-troff'``, `




```'tr'` `=&gt; ``'application/x-troff'``, `




```'roff'` `=&gt; ``'application/x-troff'``, `




```'man'` `=&gt; ``'application/x-troff-man'``, `




```'me'` `=&gt; ``'application/x-troff-me'``, `




```'ms'` `=&gt; ``'application/x-troff-ms'``, `




```'ustar'` `=&gt; ``'application/x-ustar'``, `




```'src'` `=&gt; ``'application/x-wais-source'``, `




```'xhtml'` `=&gt; ``'application/xhtml+xml'``, `




```'xht'` `=&gt; ``'application/xhtml+xml'``, `




```'zip'` `=&gt; ``'application/zip'``, `




```'au'` `=&gt; ``'audio/basic'``, `




```'snd'` `=&gt; ``'audio/basic'``, `




```'mid'` `=&gt; ``'audio/midi'``, `




```'midi'` `=&gt; ``'audio/midi'``, `




```'kar'` `=&gt; ``'audio/midi'``, `




```'mpga'` `=&gt; ``'audio/mpeg'``, `




```'mp2'` `=&gt; ``'audio/mpeg'``, `




```'mp3'` `=&gt; ``'audio/mpeg'``, `




```'aif'` `=&gt; ``'audio/x-aiff'``, `




```'aiff'` `=&gt; ``'audio/x-aiff'``, `




```'aifc'` `=&gt; ``'audio/x-aiff'``, `




```'m3u'` `=&gt; ``'audio/x-mpegurl'``, `




```'ram'` `=&gt; ``'audio/x-pn-realaudio'``, `




```'rm'` `=&gt; ``'audio/x-pn-realaudio'``, `




```'rpm'` `=&gt; ``'audio/x-pn-realaudio-plugin'``, `




```'ra'` `=&gt; ``'audio/x-realaudio'``, `




```'wav'` `=&gt; ``'audio/x-wav'``, `




```'pdb'` `=&gt; ``'chemical/x-pdb'``, `




```'xyz'` `=&gt; ``'chemical/x-xyz'``, `




```'bmp'` `=&gt; ``'image/bmp'``, `




```'gif'` `=&gt; ``'image/gif'``, `




```'ief'` `=&gt; ``'image/ief'``, `




```'jpeg'` `=&gt; ``'image/jpeg'``, `




```'jpg'` `=&gt; ``'image/jpeg'``, `




```'jpe'` `=&gt; ``'image/jpeg'``, `




```'png'` `=&gt; ``'image/png'``, `




```'tiff'` `=&gt; ``'image/tiff'``, `




```'tif'` `=&gt; ``'image/tiff'``, `




```'djvu'` `=&gt; ``'image/vnd.djvu'``, `




```'djv'` `=&gt; ``'image/vnd.djvu'``, `




```'wbmp'` `=&gt; ``'image/vnd.wap.wbmp'``, `




```'ras'` `=&gt; ``'image/x-cmu-raster'``, `




```'pnm'` `=&gt; ``'image/x-portable-anymap'``, `




```'pbm'` `=&gt; ``'image/x-portable-bitmap'``, `




```'pgm'` `=&gt; ``'image/x-portable-graymap'``, `




```'ppm'` `=&gt; ``'image/x-portable-pixmap'``, `




```'rgb'` `=&gt; ``'image/x-rgb'``, `




```'xbm'` `=&gt; ``'image/x-xbitmap'``, `




```'xpm'` `=&gt; ``'image/x-xpixmap'``, `




```'xwd'` `=&gt; ``'image/x-xwindowdump'``, `




```'igs'` `=&gt; ``'model/iges'``, `




```'iges'` `=&gt; ``'model/iges'``, `




```'msh'` `=&gt; ``'model/mesh'``, `




```'mesh'` `=&gt; ``'model/mesh'``, `




```'silo'` `=&gt; ``'model/mesh'``, `




```'wrl'` `=&gt; ``'model/vrml'``, `




```'vrml'` `=&gt; ``'model/vrml'``, `




```'css'` `=&gt; ``'text/css'``, `




```'html'` `=&gt; ``'text/html'``, `




```'htm'` `=&gt; ``'text/html'``, `




```'asc'` `=&gt; ``'text/plain'``, `




```'txt'` `=&gt; ``'text/plain'``, `




```'rtx'` `=&gt; ``'text/richtext'``, `




```'rtf'` `=&gt; ``'text/rtf'``, `




```'sgml'` `=&gt; ``'text/sgml'``, `




```'sgm'` `=&gt; ``'text/sgml'``, `




```'tsv'` `=&gt; ``'text/tab-separated-values'``, `




```'wml'` `=&gt; ``'text/vnd.wap.wml'``, `




```'wmls'` `=&gt; ``'text/vnd.wap.wmlscript'``, `




```'etx'` `=&gt; ``'text/x-setext'``, `




```'xsl'` `=&gt; ``'text/xml'``, `




```'xml'` `=&gt; ``'text/xml'``, `




```'mpeg'` `=&gt; ``'video/mpeg'``, `




```'mpg'` `=&gt; ``'video/mpeg'``, `




```'mpe'` `=&gt; ``'video/mpeg'``, `




```'qt'` `=&gt; ``'video/quicktime'``, `




```'mov'` `=&gt; ``'video/quicktime'``, `




```'mxu'` `=&gt; ``'video/vnd.mpegurl'``, `




```'avi'` `=&gt; ``'video/x-msvideo'``, `




```'movie'` `=&gt; ``'video/x-sgi-movie'``, `




```'ice'` `=&gt; ``'x-conference/x-cooltalk'``, `




```); `




`?>`
