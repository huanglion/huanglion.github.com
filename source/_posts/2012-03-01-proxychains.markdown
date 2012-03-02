---
layout: post
title: "proxychains"
date: 2012-03-01 15:09
comments: true
content: ProxyChains
categories: 
---
[ProxyChains](http://sourceforge.net/projects/proxychains/ "ProxyChains - HTTP and SOCKS") 很好用，配合[WallProxy](http://code.google.com/p/wallproxy-plugins/downloads/list "a Powerful GAE/PHP proxy with BEST Security which is Easy to use")的话。

在搭建OctoPress的时候，安装过程中要下载一个100K的文件，却老是报错，一看是连接被重置了N多。先是想用VPN，但没找到好用的，只能找其它代理了。wallProxy刚好可以用socks代理的，就用proxyChains。

在Ubuntu里可以直接安装，其他系统就没试过。
```bash
$sudo apt-get install proxychains
```
然后再修改proxychains的配置文件`sodo vim /etc/proxychains.conf`，把最后一行改成自己要用的代理。
```ruby
socks5 127.0.0.1 8086 #socks5适合比较多的软件，关键还是WallProxy/GAE支持
```
