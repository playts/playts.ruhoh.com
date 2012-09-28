---
title:
date: '2012-09-28'
description: CSS 3 linear-gradient 的语法以及常用浏览器的支持使用。
categories:
tags: CSS
---
以往编写 CSS 时都是基于CSS 2，对于 CSS 3 的新特性也是心血来潮时尝试一下，努力地搜集相关的资料信息，当尝试完毕后，这些信息慢慢被遗忘。

最近又开始折腾HTML5和CSS3相关的主题，不得再次搜集资料信息。

W3C 官网的资料：http://www.w3.org/TR/css3-images/#linear-gradients

语法：

    <linear-gradient> = linear-gradient(
      [ [ <angle> | to <side-or-corner> ] ,]? 
      <color-stop>[, <color-stop>]+
    )
我的英文太差，只能理解一部分，所以讲一讲自己的领会吧

参考这篇文章： http://css-tricks.com/css3-gradients/

    .gradient-bg {
       /* fallback/image non-cover color */
       background-color: #1a82f7; 

       /* fallback image */
       background-image: url(images/fallback-gradient.png); 

       /* Safari 4+, Chrome 1-9 */
       background-image: -webkit-gradient(linear, 0% 0%, 0% 100%, from(#2F2727), to(#1a82f7));

       /* Safari 5.1+, Mobile Safari, Chrome 10+ */
       background-image: -webkit-linear-gradient(top, #2F2727, #1a82f7); 

       /* Firefox 3.6+ */
       background-image: -moz-linear-gradient(top, #2F2727, #1a82f7);
     
       /* IE 10+ */
       background-image: -ms-linear-gradient(top, #2F2727, #1a82f7);

       /* Opera 11.10+ */
       background-image: -o-linear-gradient(top, #2F2727, #1a82f7);
    }

上面的代码对于 IE 10 以下的版本 是不起作用的，想要增加 IE 10 以下的版本的支持

    .gradient-bg
    filter: progid:DXImageTransform.Microsoft.gradient(GradientType=0, startColorstr=#1471da, endColorstr=#1C85FB);
    -ms-filter: "progid:DXImageTransform.Microsoft.gradient (GradientType=0, startColorstr=#1471da, endColorstr=#1C85FB)";
    }

"filter" 仅支持 IE 6 - IE 8 的版本
"-ms-filter" 仅支持 IE 8 以上的版本

最好的做法是：建一个IE专用的样式表

我又找到这个网站（ http://css3please.com/ ），非常赞！

代码：

    .box_gradient {
      background-color: #444444;
      background-image: -webkit-gradient(linear, left top, left bottom, from(#444444), to(#999999)); /* Safari 4+, Chrome */
      background-image: -webkit-linear-gradient(top, #444444, #999999); /* Chrome 10+, Safari 5.1+, iOS 5+ */
      background-image:    -moz-linear-gradient(top, #444444, #999999); /* Firefox 3.6-15 */
      background-image:      -o-linear-gradient(top, #444444, #999999); /* Opera 11.10-12.00 */
      background-image:         linear-gradient(to bottom, #444444, #999999); /* Firefox 16+, IE10, Opera 12.50+ */
    }

