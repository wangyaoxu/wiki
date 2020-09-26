---
title: "Git"
date: 2015-11-08 00:02
updated: 2017-12-20 16:10
collection: "版本控制管理"
tag: git
---

[TOC]

```bash
# basic

git init
git clone <repo>
git config user.name <name>
git add <dir>
git commit -m "comment message"
git status 
git log 


# branch

git branch
git checkout -b <branch>
git merge <branch>


# config 

git config --global user.name <name>
git config --global user.email <email>
git config --global alias. <alias-name> <git-command>
git config --global --edit  # Open the global configuration file and edit

# Diff

git diff HEAD
git diff --cached

# log

git log 
git log --online 
git log -p

# remote 
git remote add <name> <url>
git fetch <remote> <branch>
git pull <remote>
git push <remote> <branch>
```
![img](https://cs-notes-1256109796.cos.ap-guangzhou.myqcloud.com/7a29acce-f243-4914-9f00-f2988c528412.jpg)