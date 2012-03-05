---
layout: post
title: "vim新建文件的模板"
date: 2012-03-05 13:59
comments: true
categories: 
---
在新建文件时，如果有针对该文件扩展名的模板存在，那么模板中的内容，将被自动插入进新文档中。将模板以正确的扩展名保存至`Vim/myTemplate`目录中。如果没有myTemplate目录，就创建一个。在Windows中，将模板文件html.tpl保存到`$Vim/vimfiles/myTemplate/`目录下；而在Mac/Liunx/Unix中，则保存模板文件至`~/.vim/myTemplate/`

在`.vimrc`或`_vimrc`文件中，修改一些配置：
```vim
#Windows:
autocmd! BufNewFile * silent! 0r $VIM/vimfiles/myTemplate/%:e.tpl
```
```vim
#Mac/Liunx/Unix:
autocmd! BufNewFile * silent! 0r ~/.vim/myTemplate/%:e.tpl
```
在`:new test.html` / `:tabnew test.html`新建一个文件的时候，就会自动添加模板中的代码。

另外，在RedHat系列的系统(Fedora, CentOS等)里，gVim安装包叫vim-X11。
