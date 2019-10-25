---
layout: post
title: linux kill missions
categories: linux
description: how to kill missions in terminal
keywords: mission, linux
---
```shell
ps -ef | grep mission_name | grep -v grep | awk '{print $2}' | xargs kill -9
```

ps -ef 用于获取当前系统所有进程。

grep mission_name 过滤出与“mission_name”字符相关的数据

grep -v grep 的作用是除去本次操作所造成的影响，-v 表示反向选择

awk '{print $2}' 表示筛选出我们所关注的进程号，$2 表示每行第二个变量，此命令中为进程号

xargs kill -9 中的 xargs 命令表示用前面命令的输出结果（也就是一系列的进程号）作为 kill -9 命令的参数，-9 表示强制终止，不是必须的

批量杀任务也可以用killall
```shell
killall -9 mission_name
```
