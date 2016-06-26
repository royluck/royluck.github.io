---
layout: post
title: Bootstrap实战-企业网站
category: Studying
---

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!环境内容!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ css文件夹

+ fonts文件夹

+ img文件夹

+ less文件夹

->bootstrap文件夹

->font-awesome文件夹

->__main.less(复制bootstrap)

->_carousel.less(复制bootstrap)

->_navbar.less(复制bootstrap)

->_variables.less(复制bootstrap)

->_banner.less(自定义文件)

->_buttons-custom.less(自定义文件)

->_page-contens.less(自定义文件)

->footer.less(自定义文件)

+ js文件夹

+ index.html

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!主干!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 页头区　

+ 主内容区

+ 页脚区

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!主干内容HTML!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`／××××××××××××××××××××××页头区××××××××××××××××××××××××××××／`

`<header role="banner">`

`<nav role="navigation" class="navbar navbar-default">`
 
`<div class="container">`

`<div class="navbar-header">`

...导航条　LOGO...

`</div>`

`</div>`

`</nav>`

`</header>`

---

`／××××××××××××××××××××××主内容区××××××××××××××××××××××××××××／`

`<main role="main">`

`<div class="container">`

`<div class="row">`

`<section class="content-primary col-sm-4">`

...内容...

`</section>`

`<section class="content-secondary col-sm-4">`

...内容...

`</section>`

`<section class="content-tertiary col-sm-4">`

...内容...

`</section>`

`</div>`

`</div>`

`</main>`

---

`／××××××××××××××××××××××页脚区××××××××××××××××××××××××××××／`

`<footer role="contentinfo">`

`<div class="container">`

...内容...

`</div>`

`</footer>`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!插件介绍!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ holder.js

用于为传送带动态生成占位图片

使用方法:

在主页html引用它:

`<script src="js/vendor/holder.js">`

后使用伪URL指定大小、颜色和填充文本:

`<img src="holder.js/600x480/auto/lava/textmode:literal" alt="Holder Image">`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!页头区!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`>` 把LOGO放到导航条上方

`>` 调整导航条(独立出另外一个右单元在导航条右端)

`>` 添加实用导航(添加购物车和用户单元)

`>` 调整响应式导航

`>` 调整配色

`>` 调整折叠后的导航条配色

`>` 调整水平导航条

---

+ 把LOGO放到导航条上方

1.独立创建<div class="container"></div>，并把<img>包含进去，并修改width属性。

2.通过`visible-md`、`visbile-lg`、`visible-xs`和`visible-sm`控制LOGO(该项目中有两个LOGO)，让其在中大屏显示，小屏隐藏。

+ 调整导航条(独立出另外一个右单元在导航条右端)

1.新建一个同等级的`<ul class="nav nav-navbar navbar-right"></ul>`

2.再将其`<li class="dropdown">`包含进去

3.修改细节（窄视口下，发现下拉菜单不能全宽展示，通过在_navbar.less下修改@media(..)->.open.dropdowm-menu...）

+ 添加实用导航(添加购物车和用户单元)

1.html内添加内容:

`<header role="banner">`

...

`<div class="container">`

`<div class="utility-nav">`

`<ul>`

`<li><a href="#" title="Login or Register"><i class="icon fa fa-user fa-lg"></i> <span>Log In or Register</span></a></li>`

`<li><a href="#" title="View Cart"><i class="icon fa fa-shopping-cart fa-lg"></i> <span>View Cart</span></a></li>`

`</ul>`

`</div>`

`</div>`

2.新建_banner.less,修改样式(上述utility-nav为自定义样式，非bootstrap内样式),使其定位于块元素内右上角，并修改颜色大小:

`header[role="banner"] {`

`.banner-brand {`

`padding-top: 40px;`

`}`

`> .container {`

`position: relative; // constrain absolute positioned utility nav`

`}`

`.utility-nav {`

`position: absolute;`

`top: 0;`

`right: 20px;`

`z-index: 1999;`//设置优先级，让其在窄视口下也能显示

`> ul {`

`list-style: none;`

`> li {`

`float: left;`

`> a {`

`display: inline-block;`

`padding: 8px 12px;`

`&:hover {`

`text-decoration: none;`

`}`

+ 调整响应式导航

1.让navbar-toggle按钮左浮动(_navbar.less)

`.navbar-toggle {`

`position: relative;`

`float: left;`//修改
  
`margin-left: @navbar-padding-horizontal;`//修改

`...`

2.修改购物车和用户单元样式，并通过响应式控制，让其在窄视口下，只显示购物车和用户单元的图标，隐藏文本.sr-only()(_banner.less)

`.utility-nav{`

`...`

`...`

`>a{`

`...`

`@media (max-width: (@grid-float-breakpoint - 1)) {`
	  				
`span {`
	  					
`.sr-only();`
	  				
`}`
	  				
`.icon {`
	  					
`font-size: 2em;`
	  					
`line-height: 1.2;`
	  				
`}`
	  			
`}`

}

}

+ 调整配色

略(_variable.less)

+ 调整折叠后的导航条配色(navbar-default)

1.略

2.调整navbar-toggle样式(_variable.less)

// Navbar toggle

`@navbar-default-toggle-hover-bg:           transparent;`

`@navbar-default-toggle-icon-bar-bg:        @gray;`

`@navbar-default-toggle-border-color:       transparent;`

+ 调整水平导航条(inverted navbar)(_banner.less下添加下述内容:)

`@media (min-width: @grid-float-breakpoint) {`
	
`.navbar-default {`
		
`.navbar-inverse();//kejia () he bujia() xiaoguo yiyang de !!  hanshu yinyong!!`
		
`.navbar-nav > li > a {`
			
`text-transform: uppercase;`
	    
`font-size: 82%;`
	    
`font-weight: bold;`
    
`}`
	
`}`

`}`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!主内容区!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`>` 调整中宽布局

`>` 调整标题字体大小和按钮

`>` 增大主栏

`>` 调整第三栏

`>` 针对多个视口进行微调

---

+ 调整中宽布局

把三栏`class="col-sm-4"`分别改为`class="col-md-5"`、`class="col-md-4"`和`class="col-md-3"`

+ 调整标题字体大小和按钮

1.新建_page-contents.less

2.修改样式:

`main {`

`padding-top: 20px;`

`padding-bottom: 40px;`//给<main role="main">添加上下边距

`[class*="col-"] {`

`h1, h2, h3, h4 {`//给h1~h2清除浮动，防止按键跟标题浮动并列

`clear: both;`	

`padding-top: 20px;`

`@media (min-width: @screen-sm-min) {`//中、大视口下，第二栏和第三栏的标题，向上对其;而窄视口下，依然上下保持间距

`&:first-child {`

`margin-top: 0;`

`padding-top: 0;`

`}}}}`

+ 增大主栏(即增加第一栏字体、按键等的大小和自定义按键样式)

1.自定义按键样式:

通过函数`.button-variant(@btn-feature-color;@btn-feature-bg;@btn-feature-border)`

+ 调整第三栏(修改样式大小和颜色等)

1.略

+ 针对多个视口进行微调(调整main的上下间距等)

`@media (max-width: @screen-sm-min) {`//在单栏布局视口下，防止第二和第三栏可能会覆盖紧上方的按钮
		
`[class*="col-"] {`
			
`clear: both;`
		
`}}`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!页脚区!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`>` 准备标记(html框架)

`>` 调整布局适应平板

`<div class="col-sm-4 col-md-2" >`

`<div class="col-sm-4 col-md-2" >`

`<div class="col-sm-4 col-md-2" >`

`<div class="col-sm-12 col-md-6" >`


`>` **针对性地清除浮动**

`<div class="clearfix visible-sm"></div>`  ==>clearfix类会强制当前元素清除上方浮动，而visible-sm类则控制这个div仅在小屏幕是出现

`>` 修整细节
