---
layout : post
title : 2017-02-21工作总结
author : "Leo Qi"
Date : 2017-02-21
catalog: true
tags:
    - Java
    - Swing
    - 正则表达式
---

> 真正决定你能走多远的，是你的多维竞争力。

## 所遇问题 ##

1. 有一个输入框，只能接收英文字符，可以是大小写字母、数字和英文符号，这种情况下通常使用匹配双字节字符方法去查找是否包含非英文符号。英文符号只占一个字节。

   ```
    /**
     * 判断是否有非英文符号
     * @param string
     * @return true：有非英文符号；false:没有非英文符号
     */
    public boolean hasNotEnChar(String string) {
        // 匹配双字节字符
        String regEx = "[^\\x00-\\xff]";
        Pattern p = Pattern.compile(regEx);
        return p.matcher(string.trim()).find();
    }
   ```

## TODO ##

 1. 系统的学习正则表达式。
