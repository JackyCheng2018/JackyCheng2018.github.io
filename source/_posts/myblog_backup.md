---
title: Hexo & GitHub：GitHub上创建分支备份Blog源文件（目的：多电脑更新博客）
date: 2018-01-15 17:53:49
tags: [npm, hexo, github]
categories: 搭建博客
---
## 思路：新建hexo分支。
将博客展示文件放在master分支上
将博客源文件放在hexo分支上
<!--more-->

## 步骤
1.在github的JackyCheng2018.github.io仓库上新建一个分支hexo。然后Settings - Branches - Default branch，将默认分支改为hexo，并Update。然后将该仓库克隆到本地（我命名为myblog_backup）。
2.进去myblog_backup文件夹，输入`git branch`，显示的结果应该为`* hexo`
3.将之前的博客源文件（我的文件夹名字叫myblog），拷贝进myblog_backup文件夹
4.提交hexo分支：`git add .`、`git commit -m "backup hexo myblog"`、`git push`
5.现在就可以在JackyCheng2018.github.io仓库上看到两个分支的差异了。

## 不同电脑之间如何同步？
1.将新电脑生成的ssh key添加到github账户上
2.将JackyCheng2018.github.io仓库的hexo分支克隆到本地
3.进去文件夹执行`npm install`
4.然后就可以在新电脑上开始写博客了：`git add .`、`git commit -m "backup hexo myblog"`、`git push`。保证hexo分支版本最新，执行`hexo clean`、`hexo generate`、`hexo deploy`，博客最新改动就更新到master分支了。两个分支不干扰！

## 注意事项
每次换电脑进行博客更新时，不管上次在其他电脑有没有更新，最好先`git pull**`（这个还没实际操作过，感觉`*`前面应该有空格吧，一个`*`就可以了？）

## 疑问
我电脑里有myblog文件夹（对应master分支）和myblog_backup文件夹（对应hexo分支），每次提交hexo分支的时候，都必须先将myblog文件夹里的所有文件拷贝到myblog_backup文件夹里，然后执行`git add .`、`git commit -m "backup hexo myblog"`、`git push`才能将博客源文件和展示文件都上传到github。步骤是不是有点繁琐？而且，肯定会经常忘记拷贝的。方法还是有点问题的。应该是只有一个文件夹，只是弄两个分支。目前我还不知道方法。。。先这样

## 疑问解决了
后来所有的操作只需要在myblog_backup文件夹（对应hexo分支）操作就可以了。也就是本地myblog文件夹可以删除了。。。

## 再疑问
那为什么要在本地弄两个项目，然后抛弃一个呢？可不可以刚开始就只用一个项目开两个分支就可以了呢？






