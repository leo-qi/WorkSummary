---
layout : post
title : 2017-10-9：TextArea在Chrome下可以调整大小问题
author : "Leo Qi"
Date : 2017-10-09
catalog: true
tags:
    - TextArea
    - Chrome
    - 前段
---

1. 在使用Extjs的TextArea时发现在Chrome下会在右下角显示一个三角形，并可以拖动以改变大小。查找半天没有找到原因。后来发现并不是ExtJS引起的。而是Chrome对TextArea标签就是这样显示的。可以通过CSS来控制显示。
``
  resize: none
``
在ExtJS创建TextArea时增加CSS属性如下属性就可解决此问题。
```js
fieldStyle:'resize:none;'
```
