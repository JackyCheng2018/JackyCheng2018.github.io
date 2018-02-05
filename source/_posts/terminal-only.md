---
title: 纯用终端命令上传作品到GitHub上
date: 2018-02-05 10:32:19
tags: [npm, hexo, github,terminal]
categories: GitHub练习
---
# 步骤：
一、建立本地git仓库
cd到本地根目录
git init

二、将所有文件添加到暂存区
git add .

三、将暂存区的文件提交到仓库
git commit -m "xxxxx"

四、在GitHub上创建repository
打开https://github.com，点击Start a project，在Repository name上写上库的名字(比如我这次取的gnlyw)，点击Create repository。然后复制一下URL的链接：https://github.com/JackyCheng2018/gnlyw

五、将本地仓库关联到GitHub上
git remote add origin https://github.com/JackyCheng2018/gnlyw
如果出现错误：fatal:remote origin already exists
那就先输入git remote rm origin，
再输入git remote add origin https://github.com/JackyCheng2018/gnlyw就可以了。

六、将本地代码PUSH到GitHub远程仓库
git push -u origin master
由于新建的远程仓库是空的，所以要加上-u这个参数，以后就不用了，甚至可以用git push就可以了。

#注意事项：
一、如果库里面有README.md文件或者别的什么文件而本地没有，先pull到本地，再push
git pull --rebase origin master
如果只是写git pull，很可能需要在终端插入信息才行。按esc或者fn+esc键可以切换编辑模式和阅读模式，在阅读模式下输入":wq"保存退出。

二、如果上传的HTML文件，可以设置成能看的模式：
点Settings，找到GitHub Pages - Source，将None改成master branch，Save，然后就能看到链接https://jackycheng2018.github.io/gnlyw/，就可以在网上看了。