---
title: 如何在GitHub上添加SSH keys（只用终端命令）
date: 2018-02-08 17:34:47
tags: [npm, hexo, github,terminal]
categories: GitHub练习
---
# 步骤
一、首先检查下SSH keys是否已经存在，即id_rsa，id_rsa.pub是否存在
`ls -al ~/.ssh`

二、生成SSH keys（若SSH keys不存在）
ssh-keygen -t rsa -C "by3963air@163.com"

三、查看生成的SSH keys中的公钥
`cat ~/.ssh/id_rsa.pub`

四、将SSH keys与GitHub关联
打开https://github.com/settings/keys ，点击New SSH key，Title处随便填，Key处粘贴SSH keys中的公钥，然后点击Add SSH key

五、测试与GitHub是否绑定成功，出现successfully就说明成功了
`ssh -T git@github.com`

六、设置username和email，因为GitHub每次提交都会记录他们（这一步我也忘了我是不是这么弄的了，我好像是用的GitHub Desktop直接就匹配上了，然后没输入这个命令）
`git config --global user.name "JackyCheng2018"`
`git config --global user.email "by3963air@163.com"`

然后就可以上传作品到GitHub上或者从GitHub上clone项目到本地了。

# 插曲
用WebStorm操作的话，好像不用写步骤六