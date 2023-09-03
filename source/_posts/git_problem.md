---
title: Git的使用——failed to push some refs to报错
date: 2023/09/03  17:45:00
categories:
- [Git]
tags:
- 工具
---

Git push时的报错

<!-- more -->

## git操作

```bash
git add .
git commit -m "update"
git push
```

## 报错信息

```bash
To link
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'link'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. If you want to integrate the remote changes,
hint: use 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

## 原因

之所以出现这个报错，实际上是因为在线上库在线更改库中文件时，在本地的代码文件中不包含，所以线上代码和线下代码不一致，导致报错。

## 解决办法

将线上和线下的代码进行合并操作

```bash
git pull --rebase origin
```

之后进行push

```bash
git push
```



