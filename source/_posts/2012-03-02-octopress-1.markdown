---
layout: post
title: "octopress记录"
date: 2012-03-02 13:52
comments: true
categories: 
---
按照octopress的指导，一般自己的库的主分支（master）是octopress最后生成的静态页面。整个后台都放到source分支去。octopress整个后台都是在客户机这里的，跟wordpress的不同。

换了新机器，把库克隆下来。进入目录，切换分支到source，绝大部分的修改和更新都是这里可以完成。暂时感觉是这样，没碰到要直接在生成的页面上修改的。在切换分支后如果直接用octopress一些相关命令如：`rake new_post['title']`，会提示安装。因为在刚进入这个目录时是主分支，没有备置文件，也就没启用octopress的备置文件了。切换分支source后，换到其他目录再回来，就会提示是否启用那个备置文件。确定一下就可以了。

新的地方去更新网站页面，也要先建立下连接。`rake setup_github_pages`，输入自己的库的地址：`git@github.com:githubUser/repositoryID.git`。后面就是跟第一次使用时的一样可以`rake generate`和`rake deploy`。

octopress系统会跟踪文件的修改，比如你在预览（preview）的时候，改了样式表，刷新页面就可以看到效果了。所有样式都可以在`sass`这个文件夹里。要让字体显示是“微软雅黑”，可以在`sass/custom/_font.scss`把注释“//”去掉，再修改，`$sans: "Microsoft YaHei", "Optima", sans-serif;`。把所有链接的下划线去掉，这些链接的颜色已经足于识别了。在`sass/base/_theme.scss`修改。
