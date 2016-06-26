---
layout: post
title: Bootstrap内less文件和css类的介绍汇总
category: Studying
---

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!less文件!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

### variables.less：

+ 修改导航条样式:

(注意**navbar**和**inverted navbar**之间的区别)

`@navbar-height:                    64px;`(设置导航条高度)

`@navbar-margin-bottom:             0;`(设置导航条下边距)

`@navbar-default-color:             @gray;`(设置导航条默认颜色(即字体颜色))

`@navbar-default-bg:                #fff;`(设置导航条默认背景颜色)

`@navbar-default-border:            @gray-light;`(设置导航条边框颜色)

`@navbar-default-link-color:                @navbar-default-border;`(设置链接默认颜色(即字体颜色))

`@navbar-default-link-hover-color:         @link-hover-color;`(设置链接hover时颜色)

`@navbar-default-link-hover-bg:             @off-white;`(设置链接hover时背景颜色)

`@navbar-default-link-active-color:         @link-hover-color;`(设置链接active激活时颜色)

`@navbar-default-link-active-bg:            @gray-lightest;`(设置链接active激活时背景颜色)

`@navbar-default-link-disabled-color:       @gray-lighter;`(??)

`@navbar-default-link-disabled-bg:          transparent;`(??)

---

`@grid-float-breakpoint:` 这个变量决定了导航条在窄视口折叠，在宽视口中展开。

### navbar.less：

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!CSS类!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`visible-md`、`visbile-lg`、`visible-xs`和`visible-sm` 

==>控制块元素，让其在对应的屏大小下显示

---

`pull-right`和`navbar-right`的区别!!!

==> pull-right用于控制块元素右浮动。如下:(此时按键btn会右浮动于col-sm-4中)

---

`<div class="col-sm-4">`

`<h2>Welcome!</h2>`

`<p>Donec at ultrices est.</p>`

`<p><a href="#" class="btn btn-primary pull-right">See our portfolio <span class="icon fa fa-arrow-circle-right"></span></a></p>`

`</div>`

==> navbar-right用于专门的下拉菜单，在宽视口下，右浮动，窄视口下，不右浮动。

---

`.sr-only()` 

==>在这个媒体查询中，使用类.sr-only()作为混入，对除屏幕阅读器之外的所有设备隐藏文本.

---

`.button-variant(@btn-feature-color;@btn-feature-bg;@btn-feature-border)` 

==>快速自定义按键样式

---

`btn-lg`、`btn-xs`

==>快速设置按键样式大小，如:`a.btn{.btn-lg;background-color:@gray-light;}`

---

`darken(@btn-default-bg,5%);` 

=>设置样式颜色灰度比例,如下代码:`border-color: darken(@navbar-inverse-bg, 7%);`

---

`<div class="clearfix visible-sm"></div>` 

==>clearfix类会强制当前元素清除上方浮动，而visible-sm类则控制这个div仅在小屏幕是出现

---

`.center-block( )`

==>这个混入会对元素应用自动的左右边距，如下代码:`{width:320px;.center-block( )}`

---

`.button-varaint( )`

==>这个简洁的混入函数就会给按钮及其悬停、活动状态生成对应的样式，如下代码:`.btn {.button-variant(#fff; @brand-primary; darken(@brand-primary, 5%));}`
