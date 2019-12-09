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
isa 函数
测试对象是否具有给定类型并返回 true 或 false：
```julia
julia> isa(123,Int64)
true
```

typeof函数
返回其参数的类型：
```julia
julia> typeof(Float64)
DataType
```

复合类型
复合类型是变量名域的集合。下例中，使用struct关键字，快速定义复合类型Person：

```julia
julia> struct Person
name::String
age::Int64
end

julia> Jack = Person("Jack",27)
Person("Jack", 27)

julia> typeof(Jack)
Person

julia> Jack.name
"Jack"

julia> Jack.age
27
```
变参函数
所谓变参，是指函数中参数的个数不定，在使用时根据实际情况变化，定义函数时，最后一个参数后紧跟省略号 ... 来定义变参函数：
```julia
julia> vf(a,b,c...) = (a,b,c)

julia> vf(1,2)
(1, 2, ()))

julia> vf(1,2,3,4,5,6)
(1, 2, (3, 4, 5, 6))
```

可选参数
函数入参中，个别参数为可选项，可以不传入，因为在函数定义时设定了默认值，比如我们定义函数oa()：

```julia
function oa(x, y, z = 100)
  return x+y+z
end

julia> oa(1,2)
103

julia> oa(1,2,3)
6
```


点语法在函数应用中的场景
科学严谨地描述是：给定函数f(x)应用于数组的每个元素A以产生新的数组f(A)。即：给定一个函数f(x)，一个数组A，要把数组A中每个数都代入f(x)计算，计算结果生成新的数组。
通常而又朴素的编程技巧告诉我们，我们需要实现得到数组A长度，并声明一个数组B和数组A等长，再建立一个循环体，把f(x)置于循环体内，依次代入数组A的每个数值，并把计算结果放入数组B。
Julia提供了点语法“.”。
下面以cosd()函数的使用举例：
```julia
julia> a = [0,60,90,120,180]
5-element Array{Int64,1}:
   0
  60
  90
 120
 180

julia> cosd.(a)
5-element Array{Float64,1}:
  1.0
  0.5
  0.0
 -0.5
 -1.0
 ```
 再以梯形面积公式举例：
 ```julia
 julia> a = [10,30,60]
3-element Array{Int64,1}:
 10
 30
 60

julia> b = [20,50,100]
3-element Array{Int64,1}:
  20
  50
 100

julia> h = [100,50,20]
3-element Array{Int64,1}:
 100
  50
  20

julia> f(x,y,h) = (x + y) * h /2
f (generic function with 2 methods)

julia> f.(a,b,h)
3-element Array{Float64,1}:
 1500.0
 2000.0
 1600.0
 ```
