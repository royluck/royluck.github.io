---
layout: post
title: CSS之清除浮动
category: Studying
---

+ 1.在最后一个设置浮动的子元素后加一个空div，清除浮动；

    ` <div style="clear: both;"></div>`

+ 2.父元素设置`overflow：hidden属性；`（`overflow:auto;`也可以）但有bug，有时会出现框框

+ 3.不要浮动，子元素使用`display:inline-block;`

+ 4.父元素加高`height`属性;

