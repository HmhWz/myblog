---
title: git笔记
date: 2017-04-10 23:24:39
tags:
categories: tools
---

我的第一篇博客，或许叫做笔记更好，这篇文章主要是讲一些git的基础用法（高深的我也写不出 #手动滑稽）。

## 介绍
git是一个十分强大的分布式版本控制系统，由Linux的作者linus用两周的时间制作而成（是不是屌炸了），至于作者的制作缘由感兴趣的可以自行百度或Google。
<!--more-->

## 安装
Linux（本人用的是Ubuntu）下的安装十分方便，进入命令行执行安装命令即可：
```bash
sudo apt-get install git
```
用Windows的童鞋可以自行到 [官网](https://git-scm.com/downloads) 下载完成安装

### git init
接下来我们开始看看git的基本使用
首先我们要来新建一个文件夹，或者进入已有的文件夹执行 git init 命令：
```bash
hmh@hmh-ubuntu:~/桌面/git_test$ git init
初始化空的 Git 仓库于 /home/hmh/桌面/git_test/.git/
hmh@hmh-ubuntu:~/桌面/git_test$ 
```

### git add
这样我们便把这个文件夹初始化为了我们的git仓库，但是这还不够，因为里面的文件并没有被git跟踪，我们可以通过 git add 命令将文件添加到git暂存区，比如这个文件夹下有一个叫index.txt的文件:
```bash
hmh@hmh-ubuntu:~/桌面/git_test$ git add index.txt
hmh@hmh-ubuntu:~/桌面/git_test$ 
```
这样我们便让index.txt这个文件加入到暂存区了，但是在我们实际做项目的时候往往一下会添加/修改/删除多个文件，这样我们就不能一个个来添加了，这时就要用到 *git add -A* 这个命令了，这个命令会把文件夹下的所有改动添加到暂存区。

### git commit
git 文件实际上总共有三个状态，已修改的（就是你对某个文件做了修改还没有add到暂存区），已暂存的（通过add命令添加后的），已提交的（通过 git commit 命令提交，这样文件就真正被保存到数据库中了）。
```bash
hmh@hmh-ubuntu:~/桌面/git_test$ git commit -m "files has been committed."
[master （根提交） d5ef89f] files has been committed.
 1 file changed, 1 insertion(+)
 create mode 100644 index.txt
hmh@hmh-ubuntu:~/桌面/git_test$ 
```
上面的 *-m "files has been committed."* 是对本次提交的说明。

### git push
通常我们要让本地管理的git仓库连接到远程仓库，比如 github。那么我们可以使用 git push 命令将本地仓库推送到远程仓库实现更新。当然前提是我们本地的git仓库与某个远程仓库关联了。所以推送之前我们需要用 git remote add origin "https://github.com/yourname/yourprojectname.git" 来关联远程仓库。
```bash
hmh@hmh-ubuntu:~/桌面/git_test$ git remote add origin "https://github.com/HmhWz/git_remote.git"
hmh@hmh-ubuntu:~/桌面/git_test$ 
```
然后使用 git push 来对远程仓库更新：
```bash
hmh@hmh-ubuntu:~/桌面/git_test$ git push -u origin master
Username for 'https://github.com': HmhWz
Password for 'https://HmhWz@github.com': 
对象计数中: 3, 完成.
写入对象中: 100% (3/3), 215 bytes | 0 bytes/s, 完成.
Total 3 (delta 0), reused 0 (delta 0)
To https://github.com/HmhWz/git_remote.git
 * [new branch]      master -> master
分支 master 设置为跟踪来自 origin 的远程分支 master。
hmh@hmh-ubuntu:~/桌面/git_test$ 
```
 -u 参数是为了指定一个默认主机，后面更新不需要了。
由于时间关系后面的命令在这里就不一一详解了，下面列出一些我认为比较常用的命令供参考：
git init //初始化仓库
git add file //添加改动的文件到暂存区
git commit -m "description" //提交改动的文件并加以描述
git diff //add 文件后提交前 可以查看文件改动情况
git status //查看当前仓库状态
git log (--pretty=oneline) //查看各个版本改动情况
git reset --hard 版本号 //回到指定版本
git reflog //查看每个历史命令
git remote add origin <仓库地址> //将本地库关联到github上
git push -u origin master //首次将master分支的内容推送到github上
git push origin master //将本地内容推送到github
git pull //拉取github上的更新到本地
git branch //显示所有分支
git branch branchname 创建一个新分支
git checkout name 切换到这个分支
git checkout -b branchname 切换到一个新分支，相当于上面两个命令的合并
git merge branchName 合并指定分支到当前分支
git branch -d branchName 删除分支

