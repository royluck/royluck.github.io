---
layout: post
title: Bootstrap实战-单页营销网站
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

->_pricing-tables.less(复制bootstrap)

->_variables.less(复制bootstrap)

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

`<div class="navbar-header">`//LOGO和按钮

`<button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">`

`<span class="icon-bar"></span>`

`<span class="icon-bar"></span>`

`<span class="icon-bar"></span>`

`</button>`

`<a class="navbar-brand" href="index.html"><img src="img/logo.png" alt="Bootstrappin'" width="120"></a>`

`</div>`

`<div class="navbar-collapse collapse">`//导航项

`<ul class="nav navbar-nav">`

`<li class="active"><a href="#welcome">Welcome</a></li>`

`<li><a href="#features">Features</a></li>`

`<li><a href="#impact">Impact</a></li>`

`<li><a href="#signup">Sign Up</a></li>`

`</ul>`

`</div>`

`</div>`

`</nav>`

`</header>`

---

`／××××××××××××××××××××××主内容区××××××××××××××××××××××××××××／`

`<main role="main">`

(>>section id="welcome")

`<section id="welcome" class="jumbotron">`
        
`<div class="container">`
          
`<h1><strong>Big</strong> Welcome Message</h1>`
          
`<p>Ingenious marketing copy. And some <em>more</em> ingenious marketing copy.<a href="#features" class="btn btn-lg btn-primary pull-right">Learn more <span class="icon fa fa-arrow-circle-down"></span></a></p>`
        
`</div>`
      
`</section>`

(>>section id="features")

`<section id="features">`

`<div class="container">`

`<h1>Features</h1>`

`<div class="row">`

`<div class="features-item col-md-4">`

`<span class="icon fa fa-cloud"></span>`


`<h2>Feature 1</h2>`

`<p>Donec id elit non mi porta gravida at eget metus. Fusce dapibus, tellus ac cursus commodo. </p>`

`</div>`

...(col-md-4)*5...

`</div>`
        
`</div>`
      
`</section>`

(>>section id="impact")

`<section id="impact">`
        
`<div class="container">`
          
`<h1>Impact</h1>`
          
`<div class="reviews">`
            
`<div class="hreview review-item-1 thumbnail">`
              
`<img src="img/smiling1-by-RomainGuy-600x900.jpg" alt="Customer Photo1">`
              
`<div class="caption">`
                
`<blockquote class="description"><p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin euismod, nulla pretium commodo ultricies</p></blockquote>`
                
`<p class="reviewer">Smiling Customer1</p>`
              
`</div>`
            
`</div>`

...(hreview)*6...

`</div>`
        
`</div>`
      
`</section>`

(>>section id="signup")

`<section id="signup">`

`<div class="container">`

`<h1>Sign up now!</h1>`

`<div class="package package-basic col-md-4">`

`<table class="table table-striped">`

`<thead>`

`<tr>`

`<th colspan="2">`

`<h2>Basic Plan</h2>`

`<div class="price">$19</div>`

`</th>`

`</tr>`

`</thead>`

`<tfoot>`

`<tr><td colspan="2"><a href="#" class="btn">Sign up now!</a></td></tr>`

`</tfoot>`

`<tbody>`

`<tr><td>Feature</td><td>Name</td></tr>`

`<tr><td>Feature</td><td>Name</td></tr>`
              
`</tbody>`
           
`</table>`
          
`</div>`

...(package)*2...

`</div>`

`</section>`

`／××××××××××××××××××××××页脚区××××××××××××××××××××××××××××／`

`<footer role="contentinfo">`

`<div class="container">`

`<p class="copyright"><a href="index.html"><img src="img/logo.png" width="80" alt="Bootstrappin'"></a></p>`

`<p class="photo-credits"><a href="photo-credits.html" title="Photo Credits">Photo Credits</a></p>`

`</div>`

`</footer>`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!插件介绍!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ masonry.pkgd.min.js插件

用于多图片的响应式布局

**使用方法:**

1.下载masonry.pkgd.min.js，将其下载好之后，复制全部内容粘贴至plugin.js文本后面.

2.在主页html引用它:

先给指定的父元素添加js-masonry类，这样插件就会知道要在哪里起作用。

然后添加属性data-masonry-options。

`<div class="reviews js-masonry" data-masonry-options='{"itemSelector":".hreview"}'`//注:.hreview为.reviews内所包含的块元素

---

+ Bootstrap的ScrollSpy插件

为导航条添加ScrollSpy(配置顶部的导航条，令其对应页面中的位置)

**使用方法:**

1.在主页html引用它:

找到body标签，添加data-spy和data-target属性，如下

`<body class="homepage" data-spy="scroll" data-target=".navbar">`//data-target为指定导航栏，因为一个网页中，可能包含不止一条导航栏

2.在main.js自定义添加动画效果，如下

`$( document ).ready(function() {`
	
`$('.navbar [href^=#]').click(function (e) {`
	  
`e.preventDefault();`//取消事件的默认动作
	  
`var div = $(this).attr('href');`
	  
`$("html, body").animate({`
	    
`scrollTop: $(div).position().top`
	  
`}, "slow");`
	
`});`

`});`

---

+ TouchSwipe插件

让传送带支持轻扫手势

**使用方法:**

1.将jquery.touchSwipe.min.js内容复制到plugin.js中

2.打开main.js文件，添加如下代码保存即可(该实例支持chapter2)

`$( document ).ready(function() {`

// Set carousel options

`$('.carousel').carousel({`

`interval: 8000 `// 8 seconds vs. default 5

`});`


//Enable swiping...

`$(".carousel-inner").swipe( {`
		
//Generic swipe handler for all directions
		
`swipeRight:function(event, direction, distance, duration, fingerCount) {`
			
`$(this).parent().carousel('prev');`
		
`},`
		
`swipeLeft: function() {`
			
`$(this).parent().carousel('next');`
		
`},`
		
//Default is 75px, set to 0 so any distance triggers swipe
		
`threshold:0`
	
`});`

`});`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!页头区!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`>` 通过_variable.less调整导航条的变量(高度、外边距、颜色、悬停颜色等)

// Basics of a navbar

`@navbar-height:                    56px; `// edited

`@navbar-margin-bottom:             0; `// was @line-height-computed

...

// Navbar links

`@navbar-default-link-color:                @navbar-default-color; `// edited

`@navbar-default-link-hover-color:          #fff; `// edited

`@navbar-default-link-hover-bg:             @gray; `// edited

`@navbar-default-link-active-color:         #fff; `// edited

`@navbar-default-link-active-bg:            @gray-dark;` // edited

`>` 调整导航条切换按钮(navbar-default-toggle)的变量(去除hover背景颜色、修改icon-bar背景颜色、去除border外边框、去除其圆角radius)

// Navbar toggle

`@navbar-default-toggle-hover-bg:           transparent;` // edited

`@navbar-default-toggle-icon-bar-bg:        @gray-light;` // edited

`@navbar-default-toggle-border-color:       transparent;` // edited

`@border-radius-base:             0;` // was 4px

`@border-radius-large:            0;` // was 6px

`@border-radius-small:            0;` // was 3px

`>` 调整.navbar-brand内边距(以便与LOGO图片保持一定距离)(_navbar.less)

`.navbar-brand {`

`float: left;`

`// padding: @navbar-padding-vertical @navbar-padding-horizontal;`

`padding: 12px 30px 0 15px; // to allow for logo image`

`font-size: @font-size-large;`

...

`}`

.navbar-brand用于放置网站的文字LOGO或图片LOGO，如下:

`<a class="navbar-brand" href="index.html"><img src="img/logo.png" alt="Bootstrappin'" width="120"></a>`

`>` 自定义导航条展开时(`media(min-width:@grid-float-breakpoint)`)的列表项样式(添加左右内边距，并把文本转换成大写(uppercase))

`@media (min-width: @grid-float-breakpoint) {`
    
`float: left;`
    
`margin: 0;`

`> li {`
      
`float: left;`
     
`> a {`
        
`padding-top: ((@navbar-height - @line-height-computed) / 2);`
        
`padding-bottom: ((@navbar-height - @line-height-computed) / 2);`
        
`padding-left: 24px; `// 添加
        
`padding-right: 24px; `// 添加
        
`text-transform: uppercase; `// 添加
      
`}}}`

---

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!主内容区!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`>` 定制高清图(进入网站首页，映入眼帘的第一张欢迎展示图,其内容由图片跟文字内容块组成)

---

+ 定制高清图

1.html内容结构如下:

`<main role="main">`

(>>section id="welcome")

`<section id="welcome" class="jumbotron">`
        
`<div class="container">`
          
`<h1><strong>Big</strong> Welcome Message</h1>`
          
`<p>Ingenious marketing copy. And some <em>more</em> ingenious marketing copy.<a href="#features" class="btn btn-lg btn-primary pull-right">Learn more <span class="icon fa fa-arrow-circle-down"></span></a></p>`
        
`</div>`
      
`</section>`

2.less控制(_page-contents.less):

-->(**以992px为分界限**，当@media(max-width:@screen-sm-max)时，背景图片选用用906*600像素；当@media(min-width:@screen-md-min)时，背景图片选用1600*1060像素)

`#welcome{`
	
`height: 330px;`
	
`background-color: #191919;`
	
`color: #fff;`

`@media(max-width:@screen-sm-max){`//小屏下，使用906*600像素大小背景图片
		
`background: #191919 url('../img/subway-906x600.jpg') center center no-repeat;`
	
`}`
		
`@media (min-width:@screen-sm-min) `{//768px
		
`height: 480px;`

`}`

`@media(min-width:@screen-md-min){`//中大屏上，使用1600*1060像素大小背景图片
			
`height: 480px;`
			
`background: #191919 url('../img/subway-1600x1060.jpg') center center no-repeat;`
			
`-webkit-background-size:cover;-moz-background-size:cover;-o-background-size:cover;background-size:cover;`
		
`}}`

-->调整文字内容块，使其能相对照片定位,观察效果，根据效果调整，@media(min-width:@screen-sm-min)时,相对定位值是`right:20%;`@media(min-width:@screen-md-min)时,相对定位值是`right:50%`;

`#welcome{`
	
`position: relative;`
	
`.welcome-message{`//默认小屏下的属性控制
	
`background-color: hsla(0, 0, 1%, 0.4);`
		
`position: absolute;`
		
`top: 0;`
		
`bottom: 0;`
		
`left: 0;`
		
`right: 0;`
		
`padding: 30px 40px;`
		
`strong{`
			
`font-size: 1.5em;`
			
`text-transform: uppercase;`
		
`}}`
		
`@media (min-width:@screen-sm-min) {`//768px以上时的属性控制下
		
`height: 480px;`
		
`.container{`
			
`position: relative;`
		
`}`
		
`.welcome-message{`
			
`right: 20%;`
			
`bottom: auto;`
			
`strong{`
				
`display: block;`//"BIG"独立一行
			
`}}}`
		
`@media(min-width:@screen-md-min){`//中大屏下的属性控制
			
`height: 480px;`
			
`.welcome-message{`
				
`right: 50%;`
			
`}}}`

`>` 美化功能列表

(1.使内容居中对齐，增加内边距和高度，并调整icon大小。2.实现中大屏时三列布局，小屏时两列布局，超小屏时一列布局`(col-s-6、col-md-4)`。3.观察各响应情况，调整美化)

`#features {`
	
`.features-item {`
		
`text-align: center;`
		
`padding: 20px;`
		
`height: 270px;`
		
`.icon {`

`font-size: 90px;`//调整icon大小
		
`}`
		
`@media (max-width: @screen-xs-max) {`
			
`max-width: 320px;`
			
`.center-block();`
		
`}}}`

`>` **!!!**装饰用户评论去(其表现形式类似于上面的定制高清图，但两者的html结构形式不同!!上述使用背景图片的形式，而这里直接插入图片，)

(1.hreview微格式。2.使用thumbnail+caption结构。3.通过设置公共类标签`.hreview .caption`设置文字块的css表现和各自类`.review-item-4 .caption`标签设置个性化css表现)

+ 使用thumbnail+caption结构

使用缩略图(thumbnail)和说明(caption)结构对每条评论给出了整体封装。Bootstrap的缩略图样式就是用来在我们期望的布局中限制图片和说明的比例。

+ blockquote标签

`<blockquote>` 与 `</blockquote>` 之间的所有文本都会从常规文本中分离出来，经常会在左、右两边进行缩进（增加外边距），而且有时会使用斜体。也就是说，块引用拥有它们自己的空间。

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
