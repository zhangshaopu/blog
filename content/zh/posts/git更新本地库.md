---
title: "Git更新本地库"
date: 2020-02-15T13:59:37+08:00
draft: false
tags: [git]
categories: [tech,git]
---

## 一、查看git远程仓库地址
```
git remote -v
需要添加则 git remote add <origin(名字)> <url>
需要改则先删除  git remote rm origin

```

## 二、更新本地库代码的两种方式
1. 法一
```html
$git fetch origin master  从远程的origin仓库的master分支下载代码到本地的origin master
 
$git log -p master.. origin/master  比较本地的仓库和远程参考的区别
 
$git merge origin/master  把远程下载下来的代码合并到本地仓库，远程的和本地的合并
```
2. 法二
```html
$git fetch origin master:temp  从远程的origin仓库的master分支下载到本地并新建一个分支temp
 
$git diff temp  比较master分支和temp分支的不同
 
$git merge tem  合并temp分支到master分支
 
$git branch -d temp  删除temp
```

## 版本回退

1. 命令显示从最近到最远的提交日志
```
git log
```
2. 回退
```
git reset --hard <版本号>（只需要前面4位，git自己补全）
```


