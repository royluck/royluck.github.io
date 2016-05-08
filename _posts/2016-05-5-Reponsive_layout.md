---
layout: post
title: 响应式布局
category: Studying
---

+ 设计原则：

移动优先:在设计的初期就要考虑的页面如何在多终端展示.

渐进增强:充分发挥硬件设备的最大功能.

---

+ 实现方法:

CSS3-Media Query(最简单的方式)

借助原生Javascript(成本高,不推荐使用)

第三方开源框架(Bootstrap...可以很好的支持浏览器响应式布局的设计)

---

+ CSS3-Media Query

常见属性:

1.device-width,device-height---屏幕宽高(设备物理宽高)

2.width,height---渲染窗口宽高(可视区域，浏览器伸缩窗口大小)(像素)

3.orientation---设备方向

4.resolution---设备分辨率(DPI)（不同于像素）

参考代码:

`<html>`

`<head>`

`<link type="text/css" rel="stylesheet" href="link.css" media="only screen and (max-width:480px)"/>`//外联方式调用

`<style>`

`@media screen and(min-width:480px){ `//内嵌方式

`...`

`}`

`</style>`

`</head>`

`<body>`

`</body>`

`</html>`

---

+ 栅格系统(Grid system)

[即为列布局](http://v3.bootcss.com/css/)

+ 关键字汇总

##col 单元格##

.col-xs-

.col-sm-

.col-md-

.col-lg-

+ 一个网页兼容各屏幕分辨率实现方式:

+ 内置样式:

[可根据样式定制按钮](http://v3.bootcss.com/css/#buttons)

+ Bootstrap组件

[参考链接](http://v3.bootcss.com/components/)

+ 当自定义相关样式时，需注意!!

需避免样式冲突,因为组件本身带有Class样式


