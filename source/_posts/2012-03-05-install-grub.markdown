---
layout: post
title: "重新安装grub"
date: 2012-03-05 11:07
comments: true
categories: 
---
前几天换了主机，那个主机的CPU（E6500）支持虚拟化。原来的CPU是E5200。整个硬盘换过去。上面有三个操作系统。但WIN7直接是打不开，Ubuntu 和 Linux Mint打开以后不显示鼠标，都是显卡驱动的问题。重装WIN7，但WINDOWS不引导其他操作系统。只能再装一次GRUB去引导其他两个LINUX。

用Ubuntu的Live CD进去，找好Ubuntu的所在分区。
```ruby
sudo -i
mount /dev/sda2 /mnt
grub-install --root-directory=/mnt /dev/sda
```
`/dev/sda2`是Linux所在分区，要挂载到Live CD启动的虚拟机。
