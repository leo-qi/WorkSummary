---
layout : post
title : 2017-03-10：Linux下java Swing程序右击不能弹出JPopupMenu菜单
author : "Leo Qi"
Date : 2017-03-10
catalog: true
tags:
    - Java
    - Linux
    - Swing
    - JPopupMenu
---

> 不是最强壮的能生存，也不是最聪明的能生存，而是最适合的能生存 ——达尔文《物种起源》。

1. Swing程序中有一个Dialog，Dialog里有一个JTable，右击JTable中的行，弹出菜单。JTable用addMouseListener方法增加一个鼠标监听MouseListener。MouseListener中需要实现的有五个方法mouseReleased、mousePressed、mouseExited、mouseEntered、mouseClicked。要实现右键弹出菜单会有一个问题，并不是所有平台都是鼠标右键弹出菜单的。即使Windows下还可以设置鼠标的左右手习惯呢。所以利用鼠标事件MouseEvent的isPopupTrigger()方法来判断是不是要弹出菜单。Windows下 只要在mouseReleased()方法中判断isPopupTrigger()是不是true就可以了。因为Windows下是鼠标右键放开时弹出菜单，在其他方法中都是false。
今天的问题是在Linux下不能弹出菜单，原因是Linux下是鼠标按下时弹出菜单，也就是在mousePressed()方法中返回true，所以在mousePressed()方法中增加isPopupTrigger()增加判断，并实现弹出菜单。

2. Linux发现版本不同，有的Linux的目录名称区分大小写。