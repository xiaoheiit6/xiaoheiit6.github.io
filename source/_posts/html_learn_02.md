---
title: HTML初识——重点标签
date: 2023/08/29  14:45:00
categories:
- [HTML]
tags:
- 前端

---

**HTML重点标签**的学习记录。

<!-- more -->

## a标签详解

- 属性
  - href
  
    - 网址
  
      - 第一种：https://google.com
      - 第二种：http://google.com
      - 第三种：//google.com（官方推荐）
    - 路径
  
      - /a/b/c 以及 a/b/c
  
      - index.html 以及 ./index.html
    - 伪协议
      - javascript:代码;
      - mailto:邮箱
      - tel:手机号
    - id
      - herf=#xxx
  - target
    - 内置名字
      - _blank 在新的页面打开
      - _top 
      - _parent
      - _self 在当前页面打开
    - 程序员指定的名字
      - window的name 可以使几个跳转的a标签在同一个窗口打开
      - iframe的name
  
## img标签

- 作用
  - 发出get请求，展示一张图片
- 属性
  - alt（代替性文字，一般直接不写）
  - height/width（宽和高只指定一个，会自动缩放。或者全部按照图片原先尺寸。）
  - src（图片地址）
- 事件
  - onload（加载成功运行一个函数）
  - onerror（同理，加载失败运行一个函数）
- 响应式
  - max-width:100%（css）
- 可替换元素

  