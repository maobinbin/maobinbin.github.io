---
layout: post
title: Markdown 笔记
categories: Markdown
description: Markdown 笔记
keywords: Markdown, VSCode
---


**目录**

* TOC
{:toc}

## 背景

### 优点

1. 专注于文字内容；

2. 纯文本，易读易写，可以方便地纳入版本控制；

3. 语法简单，没有什么学习成本，能轻松在码字的同时做出美观大方的排版。

### 使用场景

* 各类代码托管平台

    主流的代码托管平台，如 GitHub、GitLab、BitBucket、Coding、Gitee 等等，都支持 Markdown 语法，很多开源项目的 README、开发文档、帮助文档、Wiki 等都用 Markdown 写作。

* 技术社区和写作平台

    StackOverflow、CSDN、掘金、简书、GitBook、有道云笔记

* 论坛

    V2EX、光谷社区

个人感觉比较遗憾的一点是各平台可能采用不同语言实现的 Markdown 解析引擎，或采用同一解析引擎的不同版本，而且可能有不同程度的定制与扩展，这导致在不同平台上使用 Markdown 写作时体验并不完全一致。不过幸好对于大家公认的一些标准语法，各家都是支持的。

### 编辑工具

理论上任何一款文本编辑器都能用于编辑 Markdown 文档，它们分别提供了不同程度的语法高亮、预览等功能，以下只是列举其中一部分，选择自己称手的即可。

* 现代编辑器

    VSCode / Atom

* 传统编辑器

    Vim / Emacs / Sublime Text / Notepad++

* IDE 自带编辑器

    IntelliJ IDEA / Android Studio / WebStorm

* 专用编辑器

    Ulysses / Mou / Typora / Markpad

## 语法

### 标题

**Markdown：**

```
# atx-style 一级标题

## 二级标题

###### 六级标题

Setext-style 一级标题
===

二级标题
---
```

**预览效果：**

> # atx-style 一级标题
> 
> ## 二级标题
> 
> ###### 六级标题
>
> Setext-style 一级标题
> ===
>
> 二级标题
> ---

**对应 HTML：**

```html
<h1>atx-style 一级标题</h1>

<h2>二级标题</h2>

<h6>六级标题</h6>

<h1>Setext-style 一级标题</h1>

<h2>二级标题</h2>
```

### 段落

中间没有空行的连续不断的几行文字被视为一个段落。

**Markdown：**

```
白日依山尽，

黄河入海流。
（句号后面没空格）

欲穷千里目，

更上一层楼。  
（句号后面有俩空格）
```

**预览效果：**

白日依山尽，

黄河入海流。
（句号后面没空格）

欲穷千里目，

更上一层楼。  
（句号后面有俩空格）

**对应 HTML：**

```html
<p>白日依山尽，</p>

<p>黄河入海流。
（句号后面没有空格）</p>

<p>欲穷千里目，</p>

<p>
  更上一层楼。
  <br>
  （句号后面有俩空格）
</p>
```

### 行内格式

对段落或者部分文本的强调效果。

**Markdown：**

```
后面俩字**加黑**

后面俩字*斜体*
```

**预览效果：**

后面俩字**加黑**

后面俩字*斜体*

**对应 HTML：**

```html
<p>
  后面俩字
  <strong>加黑</strong>
</p>
<p>
  后面俩字
  <em>斜体</em>
</p>
```

### 引用块

**Markdown：**

```
> 引用块段落一。
>
> 引用块段落二。
>> 内嵌引用块段落一。
>
> ### 引用块内的标题
```

**预览效果：**

> 引用块段落一。
>
> 引用块段落二。
>
> > 内嵌引用块段落一。
>
> ### 引用块内的标题

**对应 HTML：**

```html
<blockquote>
  <p>引用块段落一。</p>
  <p>引用块段落二。</p>
  <blockquote>
    <p>内嵌引用块段落一。</p>
  </blockquote>
  <h3 id="引用块内的标题">引用块内的标题</h3>
</blockquote>
```

### 超链接

Markdown 支持行内式链接和引用式链接。

**Markdown：**

```
行内式 [GitHub](https://github.com/mzlogin) 链接。

引用式 [GitHub][1] 链接。
[2]: https://github.com/ "GitHub 主页"
```

**预览效果：**
行内式 [GitHub](https://github.com/mzlogin) 链接。
引用式 [GitHub][1] 链接，带 title。
[1]: https://github.com " GitHub 主页"


### 图片

在超链接的写法前加一个 `!`，就是引用图片的方法。


### 列表

包括有序列表和无序列表。

**Markdown：**

```
- 苹果
- 葡萄
- 榴莲

1. 苹果
2. 葡萄
3. 榴莲
```

**预览效果：**

- 苹果
- 葡萄
- 榴莲

1. 苹果
2. 葡萄
3. 榴莲



其中无序列表的标记可以使用 `+`、`-` 或 `*`，有序列表前的数字可以是乱序的。

### 代码块

支持行内代码和代码块。

**Markdown：**

    Android 里使用 `TextUtils` 类的 `isEmpty` 方法来判断字符串是否为空。

    ```java
    if (TextUtils.isEmpty(text)) {
        return null;
    }
    ```

**预览效果：**

Android 里使用 `TextUtils` 类的 `isEmpty` 方法来判断字符串是否为空。

```java
if (TextUtils.isEmpty(text)) {
    return null;
}
```

上例中的语言标记 `java` 可选填，可用于在编辑器和渲染后的效果里添加语法高亮。

块式代码也可以对整个代码段缩进四个空格，或一个 Tab 来实现。

### 水平分割线

使用一个单独行里的三个或以上 `*`、`-` 来生产一条水平分割线，它们之间可以有空格。

**Markdown：**

```
***

-----

- - -
```

**预览效果：**

***

-----

- - -


## 扩展语法

本节的内容是介绍一些受到广泛支持的 Markdown 扩展语法。

### 表格

**Markdown：**

    | 编号  | 姓名（左） | 年龄（右） | 性别（中） |
    | ----- | :--------  | ---------: | :------:   |
    | 0     | 张三       | 28         | 男         |
    | 1     | 李四       | 29         | 男         |

**预览效果：**

| 编号  | 姓名（左） | 年龄（右） | 性别（中） |
| ----- | :--------  | ---------: | :------:   |
| 0     | 张三       | 28         | 男         |
| 1     | 李四       | 29         | 男         |



### 任务列表

在 GitHub / GitLab 里有较好的支持。

**Markdown：**

```
- [x] 洗碗
- [ ] 清洗油烟机
- [ ] 拖地
```

**预览效果：**

- [x] 洗碗
- [ ] 清洗油烟机
- [ ] 拖地



### 删除线

**Markdown：**

```
后面三个字打上~~删除线~~。
```

**预览效果：**

后面三个字打上~~删除线~~。

**对应 HTML：**

```html
<p>后面三个字打上<del>删除线</del>。</p>
```

### 自动链接

自动链接扩展，即：当识别到 URL，或用 `<`、`>` 包括的 URL 时，会自动为其生成 `a` 标签。

**Markdown：**

```
https://github.com

<example@gmail.com>
```

**预览效果：**

https://github.com

<example@gmail.com>



### emoji

以 GitHub Pages 为例。

**Markdown：**

```
:camel: :blush: :smile:
```

**预览效果：**

:camel: :blush: :smile:

<!--
## 奇技淫巧
脑洞清奇的工程师们还发掘了很多使用 Markdown 的方法，大部分都是引入第三方 JavaScript 插件来实现。对这部分我只做简述，对其中的部分功能比如作图等，还是推荐用专门的可视化工具去做。
### 画流程图和时序图
### 插入数学公式
### 用 Markdown 做 PPT
-->
