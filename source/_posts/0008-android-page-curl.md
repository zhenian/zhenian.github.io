---
title: 安卓仿真翻页小记
date: 2017-01-05 21:37:12
tags:
- Android
- page-curl
- 仿真翻页
- 阅读器
- 杂志
categories:
- 技术
---

Android 应用的设计语言是：[Material Design](https://material.io/)，Material Design 以纸墨为灵感的。但是最近做的项目的，有一个需求是做仿真翻页的。这种动画效果广泛应用在电子书，杂志等应用中。

但是研究后发现，Android 官方的标准库中并没有提交这样的动画效果，而开源的各种库也没有这样的动画效果可以快速整合到现有的UI组件中。

查看了Material design的相关文档，留意到其中说：

> Material never bends or folds.
> Material 从不弯曲或者折叠的。
>
>                  [Material Design]
([link](https://material.io/guidelines/material-design/material-properties.html#material-properties-transforming-material))

所以，一切得回到根源上去。所需要的内容，自己画。就像游戏一样。

搜索了一番之后，找到 [android_page_curl](https://github.com/harism/android_page_curl)这个项目，通过 GLSurfaceView 来实现了仿真动画。例子中提供了基于图片的实现。

基本这个例子，修改了一通之后，应用起来。

应用的关键点：

- 1. 所有的内容都自己画
- 2. 事件响应，在画内容的过程中，记录下要响应事件的区域

一个小调整后的代码在：https://github.com/zhenian/android_page_curl

--END--

