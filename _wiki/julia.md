---
layout: wiki
title: Julia
categories: Julia
description: Julia 基本语言规则
keywords: Julia, 语言规则
---

## 类型
断言运算符::
左表达式::右数据类型，判断“左表达式”是否为“右数据类型”的实例，如果true，返回“左表达式”的值，如果false，返回错误信息。
true情况，例如
```julia
julia> (9.0*9.0) :: Float64
81.0

julia> (9*9) :: String
ERROR: TypeError: in typeassert, expected String, got Int64
Stacktrace:
 [1] top-level scope at none:0
```

::在local变量时的使用
在代码块中赋值变量时，可以使用::做变量类型声明，语法：
变量名::类型 = 值
变量在赋值的同时声明类型，例如：
```julia
x :: String = "this is function local string"
```
