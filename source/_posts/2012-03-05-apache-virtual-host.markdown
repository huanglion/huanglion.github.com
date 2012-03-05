---
layout: post
title: "apache服务器设置多站点"
date: 2012-03-05 15:01
comments: true
categories: 
---
在本机的Windows下设置的。

1. 随便写个域名，如 h.co；
2. 在hosts文件里，添加`127.0.0.1 h.co`;
3. 在httpd.conf文件里添加：
```apache
#这个是把域名指到对应文件夹
<VirtualHost 188.188.8.254>
DocumentRoot "G:\www"
ServerName h.co
</Virtualhost>

#这个是给指定的文件夹一定的权限
<Directory "G:\www">
    AllowOverride None
    Options None
    Order allow,deny
    Allow from all
</Directory>
```
如果有多个域名，就多添加几个类似的内容就行了。
