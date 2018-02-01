---
title: Github入门
tags: [github]
categories: [github]
---
在忙完项目之余，自己研究了GitHub，毕竟现在用的很广泛，虽然GitHub都是大神使用的，我就当做自己的笔记库，存储一些自己平时遇到的问题时的解决方法，以方便下次浏览，希望对自己的以后前端的发展之路有所帮助。
## 上传自己的项目代码

### 1.进入Github首页，点击New repository新建一个项目（前提是有个自己的GitHub账号）

![](/images/github1.png)

### 2.填写相应信息后点击create即可 

Repository name: 仓库名称
Description(可选): 仓库描述介绍
Public, Private : 仓库权限（公开共享，私有或指定合作者）
Initialize this repository with a README: 添加一个README.md
gitignore: 不需要进行版本管理的仓库类型，对应生成文件.gitignore
license: 证书类型，对应生成文件LICENSE

![](/images/github2.png)

### 3.保留创建仓库之后界面中的地址备用

![](/images/github3.png)

### 4.接下来就到本地操作了，首先右键你的项目，如果你之前安装git成功的话，右键会出现两个新选项，分别为Git Gui Here,Git Bash Here,这里我们选择Git Bash Here

### 5.输入命令 cd Test，进入Test文件夹，以此输入以下代码即可完成剩余的操作

git init   （在目录中执行 git init，就可以创建一个 Git 仓库了）
git add .        （注：别忘记后面的.，此操作是把Test文件夹下面的文件都添加进来）
git commit  -m  "提交信息"  （注：“提交信息”里面换成你需要，如“first commit”）
git push -u origin master   （注：此操作目的是把本地仓库push到github上面，此步骤需要你输入帐号和密码）

## 对已经上传过的代码进行上传

从上面步骤的第四部开始，进入该项目的文件夹，执行以下的命令即可

git add *    （代表更新全部）
git commit -m "更新说明"    （commit只是提交到缓存区域）
git push origin master    （最后一步才是push到远程master分支上）

打开github界面就能看到同步了
