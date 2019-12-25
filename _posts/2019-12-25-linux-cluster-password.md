---
layout: post
title: 免密登陆服务器
categories: linux
description: 服务器免密登录设置
keywords: linux,cluster,password 
---


本地电脑：
```shell
ssh-keygen -t rsa
```
生成文件 ~/.ssh/id_rsa.pub

将本地电脑中文件id_rsa.pub上传到服务器
```shell
scp -r -P** ~/.ssh/id_rsa.pub username@ip:~/.ssh 
```
将公钥导入认证文件
```shell
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys   
```
