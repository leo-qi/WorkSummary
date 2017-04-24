---
layout : post
title : 2017-03-16：MyEclipse下去掉js验证
author : "Leo Qi"
Date : 2017-03-16
catalog: true
tags:
    - Java
    - JavaScript
    - MyEclipse
---

> 时间是一片片的，好像切成薄片的黄油一样，铺在不同的事情上。——《房间》。

1. 项目中使用了extjs，MyEclipse会进行js校验，占用系统资源，造成电脑很卡。在window->Preferneces->MyEclipse->Validation中去掉JavaScript validator for JS files去掉Manual和Build，不能正常生效，未找到原因。打开项目所在目录下的.project文件，去掉
```xml
<buildCommand>  
    <name>org.eclipse.wst.jsdt.core.javascriptValidator</name>  
     <arguments></arguments>  
</buildCommand>  
<nature>org.eclipse.wst.jsdt.core.jsNature</nature>  
```

其他产考[百度](http://jingyan.baidu.com/article/ca41422fe094251eae99ede7.html)
