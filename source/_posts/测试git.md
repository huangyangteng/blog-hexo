---
title: css字体与排版
date: 2019-01-06 21:06:22
tags: css
categories: css
---
> 一只**木桶**盛水的多少，并不取决于**桶**壁上最高的那块**木**块，而恰恰取决于**桶**壁上最短的那块。作为一个前端切图仔，字体知识必不可少。
>
> 阅读时间：大约5分钟，难度：非常简单

<!-- more -->

### 1. 字体来源

网页中的字体有三个来源：

* 用户机器安装的字体(可以放心使用)
* 保存在第三方网站的字体（最常见的是Typekit和Google,后文给出符合国情的链接）
* 保存在你的web服务器上的字体(这些字体可以使用@font-face规则随网页一起发送给浏览器)

首先，我们讨论如何使用那些安装在用户机器上的字体

### 2. 安装在用户机器上的字体

以下是与字体样式相关的6个属性：

* font-family
* font-size
* font-style
* font-weight
* font-variant
* font(简写属性)

我们只讨论和本文最密切的属性，**font-family**

```less
//font-family用来指定元素中的文本使用什么字体，一般来说，应该给整个页面设定一种主字体，然后只对那些需要使用不同字体的元素再应用font-family

//为整个页面指定字体：
body{
    font-family:verdana,sans-serif;
}
//注意：font-family中的值不区分大小写
```

用户机器上的字体是随操作系统一起安装的，可以在本地应用共享，也就是说，你在word中使用的字体都可以在浏览器中使用。每种操作系统自带的字体不多，而且用户可能会删除字体，因此我们永远也不敢保证一定能使用某种字体来显示网页，因此，在指定文本的字体时，需要多列出几种后备字体，以防第一种字体无效。

```less
body{
    font-family:'trebuchet ms',tahoma,sans-serif;
}
//如果字体中间有空格，需要使用引号包裹
//注意：给font-family字体列表的最后一项指定一个通用字体类非常重要，比如serif、sans-serif
```

有哪些通用的字体类呢？有以下五种：

* serif 也就是衬线字体，在每个字符笔画的末端会有一些装饰线 比如宋体 
* Sans-serif 也就是无衬线字体，没有装饰线，最常用
* Monospace,也就是等宽字体，常用于代码
* Cursive,草体或手写体
* fantasy,奇形怪状的字体

指定通用字体类可以在前面指定的字体都不存在时，从通用字体类中随机选取一种显示文本

### 3.web字体大揭秘

目前，使用@font-face规则在网页中嵌入可下载字体的css功能，已经得到了浏览器的广泛支持。[可以支持到ie6,点击查看](https://caniuse.com/#search=%40font-face)

设定web字体的方式有以下三种：

1. 使用公共字体库，比如[Google Web Fonts中文网](http://www.googlefonts.cn/)  [国内使用方法1,360镜像库](https://cdn.baomitu.com/index/fonts)  [国内使用方法2，反向代理](https://sb.sb/blog/css-cdn/)
2. 使用事先打包好的@font-face包  
3. 使用Font Squirrel等工具用你自己的字体生成@font-face包  [字蛛-中文字体压缩器](http://font-spider.org/) 







