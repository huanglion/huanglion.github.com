---
layout: post
title: "linux mint安装极点五笔"
date: 2012-03-05 14:26
comments: true
categories: 
---
按官方的[说明](http://code.google.com/p/ibus)安装ibus，但ibus没有提供极点五笔。
```bash
$ sudo add-apt-repository ppa:shawn-p-huang/ppa 
$ sudo apt-get update 
$ sudo apt-get install ibus ibus-pinyin
$ sudo apt-get install ibus-gtk ibus-qt4
$ im-switch -s ibus
```
所以还要安装ibus-table`sudo apt-get install ibus-table`，再去[下载](http://forum.ubuntu.org.cn/viewtopic.php?f=8&t=262266)极点五笔的码表并安装。
