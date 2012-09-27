---
title:
date: '2012-09-27'
description:
categories:
---
本站基于 ruhoh ，欲了解详情请移步到 http://ruhoh.com 

试用了 ruhoh 感觉挺不错，参照官网的文档记录一下常用命令

### 创建 post ###

    $ ruhoh post

将会生成： posts\untitled-post.md

    $ ruhoh post "my post title"

将会生成： posts\my-post-title.md

post 页面默认的数据如下：

    ---
    title:
    date: '2012-09-27'
    description:
    categories:
    ---

### 创建 page ###

    $ ruhoh page about.md

将会生成： pages\about.md

**创建一个子页面**

    $ ruhoh page projects/android.md

将会生成： pages\projects\android.md

**创建一个子页面，并使用“漂亮”的路径（ "pretty" path）**

    $ ruhoh page projects/android

将会生成： pages\projects\android\index.md

**指定文件扩展名**

    $ ruhoh page projects/android --ext .html

将会生成： pages\projects\android\android.html

### 插入图片： ###

    <img src="{{urls.media}}/my-media-file.jpg">

### 本地预览: ###

    $ rackup -p 9292

### 使用标签：###

请参考： http://ruhoh.com/usage/create/#toc_14

### 使用分类： ###

请参考： http://ruhoh.com/usage/create/#toc_12

### 使用草稿： ###

请参考： http://ruhoh.com/usage/create/#toc_5