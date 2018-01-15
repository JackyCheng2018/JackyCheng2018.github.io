---
title: Hexo & GitHub：部署时如何保证README.md不被渲染
date: 2018-01-09 10:52:46
tags: [npm, hexo, github]
categories: 搭建博客
---
这几天用Hexo & GitHub倒腾博客，每次一执行hexo deploy命令，README.md就得重新写，这肯定不行啊，于是我就上网找了些资料。方法如下：<!--more-->
1.找到主配置文件_config.yml，设置skip_render: README.md。
2.在/source/文件夹下新建README.md，然后以后的README就可以在这里面写了，以后hexo deploy直接将README.md一并部署了。
经过测试，可以了。
顺带说一下在README.md里插入图片的方法：
在README.md同一个文件夹下，新建一个/images/文件夹，然后把图片放里面。比如keai.jpg，然后输入```![](/images/keai.jpg)```就可以了。然后显示的就是下面的图片：<br>
![好可爱啊](/images/keai.jpg)<br>
还有就是，README.md换行是需要用```<br>```才能换行的。