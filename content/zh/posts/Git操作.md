---
title: Git 操作
date: 2020-02-09T20:56:07+08:00
draft: false
excerpt: 
toc: true
tags: [git]
categories: [tech,git]
keyword: []
--- 



# git rm 与 rm q的区别

# git branch -a
 查询分支


# git 分支创建的合并
1、切换到基础分支，如主干
```
git checkout master
```
2、创建并切换到新分支
```
git checkout -b panda
```
git branch可以看到已经在panda分支上

3、更新分支代码并提交
```
git add *

git commit -m ""
```
4、push 到远程分支panda/origin
```
git push origin origin 
git push origin panda
```
5.将某一分支合并到master分支
 1、切换到master ：git  checkout master
 2、如果是多人开发的话 需要把远程master上的代码pull下来： git pull origin master
 3、git  merge 分支名
 4、git push

6、 更新远程分支列表
```
git remote update origin --prune

```
# git add .和 git add -A区别

git add . ：他会监控<工作区的状态树>，使用它会把工作时的所有变化提交到暂存区，包括文件内容修改(modified)以及新文件(new)，但不包括被删除的文件。

git add -u ：他仅监控已经被add的文件（即tracked file），他会将被修改的文件提交到暂存区。add -u <不会提交新文件>（untracked file）。（git add --update的缩写）

git add -A ：是上面两个功能的合集（git add --all的缩写）

