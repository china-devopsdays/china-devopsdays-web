---
title: "第一次社区会议-演示投稿文章标题"
date: 2018-06-19T17:00:49+08:00
draft: false
banner: "/img/blog-bg.jpg"
author: "姓名"
summary: "文章摘要是一句话的概要说明，让读者了解这篇文章。"
tags: ["DevOps"]
categories: ["分享"]
---

向社区网站投稿的方法有两种：

* GitHub 代码投稿，提交PR
* 邮件投稿

本文主要描述代码投稿的详细步骤和方法。


包括修改投稿文章草稿的元数据字段，编辑和本地预览文章，提交代码等步骤。

## 标题

title: "My New Post Title"  - > title: "第一次社区会议演示文章标题"

## 作者

author: "投稿人"  -> author: "姓名"

## 文章摘要

summary: "文章摘要"  -> summary: "文章摘要是一句话的概要说明，让读者了解这篇文章。"

## 标签

tags: ["DevOps"]  - > tags: ["DevOps", "DevOps", "DevOps", "DevOps", "DevOps"]

不要超过10个标签，建议5个左右，中英文都可以。

## 分类 

categories: ["分享"] -> categories: ["投稿"]

投稿以后，这篇文章会被再次准确分类。

## 正文

正文用Markdown格式编写，文章的图片放在 static/blog 目录下。

建议使用微软的 Visual Studio Code 编辑器。

随时在本地浏览编辑结果，如果有什么问题，请在志愿者群里提问。

最后提交工作成果。


## 代码库git操作命令参考

以下命令是在Windows10操作系统下，在cmder命令行工具中的实际执行结果（cmder接受linux下的常用命令）。Linux和Mac OS系统也可以参考

对所有操作系统的需求如下：

* 安装git
* 安装Markdown编辑器
* 安装hugo服务器，在windows下就是一个可执行文件 hugo.exe ；把它放到合适的路径下即可。


### Fork 代码库

将网站的代码库Fork为个人的代码库。

![](/blog/fork.png)

![](/blog/fork2.png)

将社区网站的源代码，搬家到自己的GitHub账号里。

### Clone 代码库

![](/blog/clone.png)

```

#将fork的代码库，克隆到本地

λ git clone https://github.com/devopscoachorg/china-devopsdays-web.git
Cloning into 'china-devopsdays-web'...
remote: Counting objects: 685, done.
remote: Compressing objects: 100% (534/534), done.
remote: Total 685 (delta 188), reused 627 (delta 134), pack-reused 0
Receiving objects: 100% (685/685), 27.45 MiB | 671.00 KiB/s, done.
Resolving deltas: 100% (188/188), done.

#查看并进入本地代码库目录

λ ls
china-devopsdays-web/
λ cd china-devopsdays-web\


#添加上游代码库路径

λ git remote add upstream https://github.com/china-devopsdays/china-devopsdays-web.git


#查看添加后的结果

λ git remote -v
origin  https://github.com/devopscoachorg/china-devopsdays-web.git (fetch)
origin  https://github.com/devopscoachorg/china-devopsdays-web.git (push)
upstream        https://github.com/china-devopsdays/china-devopsdays-web.git (fetch)
upstream        https://github.com/china-devopsdays/china-devopsdays-web.git (push)


#签出主干分支

λ git checkout master
Already on 'master'
Your branch is up to date with 'origin/master'.

#将上游最新主干代码库更新到本地主干

λ git pull upstream master --rebase
From https://github.com/china-devopsdays/china-devopsdays-web
 * branch            master     -> FETCH_HEAD
 * [new branch]      master     -> upstream/master
Already up to date.
Current branch master is up to date.


```

### 创建分支和编辑投稿文章

```

#建立一个本地的分支，投稿文章的代码放在这里面

λ git checkout -b demo-at-1st-community-meeting
Switched to a new branch 'demo-at-1st-community-meeting'

#用Hugo命令创建文章模板
λ hugo new blog\my-new-post-title.md

#启动本地hugo服务器，本地浏览全站代码，并预览投稿的文章

λ hugo server

                   | ZH
+------------------+-----+
  Pages            |  44
  Paginator pages  |   0
  Non-page files   |   0
  Static files     | 256
  Processed images |   0
  Aliases          |  15
  Sitemaps         |   1
  Cleaned          |   0

Total in 607 ms
Watching for changes in C:\Users\Nutanix\Documents\devopsdays\china-devopsdays-web\{content,data,static,themes}
Watching for config changes in C:\Users\Nutanix\Documents\devopsdays\china-devopsdays-web\config.toml
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop

```
![](/blog/edit.png)



### 投稿文章提交

结束本地代码处理工作，提交到远程代码库。

```



#文章编辑完之后，保存本地工作结果

λ git add .                                                                                            
                                                                                                
#为本次提交添加一个有意义的注释

λ git commit -m "this post tell you how to add a new article"
[demo-at-1st-community-meeting 691ed98] this post tell you how to add a new article
 2 files changed, 41 insertions(+)
 create mode 100644 content/blog/my-new-post-title.md
 create mode 100644 static/blog/blog-bg.jpg


#推送本地工作成果到自己的远程github代码库

λ git push origin demo-at-1st-community-meeting
Counting objects: 7, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (6/6), done.
Writing objects: 100% (7/7), 1.15 KiB | 1.15 MiB/s, done.
Total 7 (delta 3), reused 0 (delta 0)
remote: Resolving deltas: 100% (3/3), completed with 3 local objects.
To https://github.com/devopscoachorg/china-devopsdays-web.git
 * [new branch]      demo-at-1st-community-meeting -> demo-at-1st-community-meeting

#本地代码操作完毕，回到网站上提交投稿PR

```

### 提交PR

从个人代码库提交投稿文章到社区代码库，这个过程需要社区网站维护团队做代码评审。评审之后，会触发Travis自动化做构建和部署。

![](/blog/pr1.png)

![](/blog/pr2.png)

![](/blog/pr4.png)

## 邮件投稿

如果以上代码操作过程，不适合您，请发邮件到 organizer@ChinaDevOpsDays.org

投稿文章要求：

* 建议 Markdown 文档格式，也接受word格式
* 文章插图的图片和文档一起打包发送
* 文章原文华为附图，一起打包为 .zip 文件
* 发邮件到投稿邮箱 organizer@ChinaDevOpsDays.org
* 等待社区的回复和处理