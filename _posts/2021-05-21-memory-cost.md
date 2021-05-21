---
layout: post
title: memory cost
categories: c++
description: some word here
keywords: memory, cost, c++
---

c++中浮点数类型：
- float:单精度32位
- unsigned float: 单精度无符号, 32位
- double：双精度, 64位
- long double：高双精度，80位

存储空间：
- 1字节(Byte)=8位(bit)
- 1KB=1024B
- 1MB=1024KB
- 1GB=1024MB
- 1TB=1024GB

$1GB \approx 10^9B \approx  10^10 bit$
float matrix with size $10000\times 10000$ cost $10^8\times 32bit\approx4\times 10^8B\approx 0.4G$

so a matrix with $10^5$ about $40G$
