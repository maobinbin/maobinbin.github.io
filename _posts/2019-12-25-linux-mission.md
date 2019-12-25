---
layout: post
title: 服务器后台提交matlab，python任务
categories: [linux, matlab, python]
description: 后台提交任务脚本
keywords: linux, matlab, python, mission
---

matlab 
```shell
nohup matlab -nojvm -nodisplay < main.m 1>running.log 2>running.err &
```

python
```shell
 nohup python < main.py 1>running.log 2>running.err &
```
