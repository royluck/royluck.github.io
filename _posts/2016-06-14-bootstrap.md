---
layout: post
title: Bootstrap实战
category: Studying
---

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 添加主结构元素：

配置好环境之后，就可以直接在`<!-- Add your site or application content here -->`注释下添加程序。

1.头部<head role="banner">(用于添加导航条等...)

`<header role="banner">`
           
`<nav role="navigation">`
   
`</nav>`
        
`</header>`

2.主内容<main role="main">

`<main role="main">`
            
`<h1>Main Heading</h1>`

`<p>Content specific to this page goes here.</p>`
       
`</main>`

3.底部<footer role="contentinfo">
        
`<footer role="contentinfo">`

`<p><small>Copyright &copy;Company Name</small></p>`
        
`</footer>`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 添加导航条

1.在上述主结构的基础下，添加两部分（一为主标题，二为副标题）。

`<header role="banner">`

4.添加了navbar-static-top类，因为我们希望导航条能够定位到窗口顶部，但能够随着页面滚动而滚动；

`<nav role="navigation" class="navbar navbar-static-top navbar-default">`

`<div class="container">`

---

2.这是主标题，主要用于放置网站logo跟链接到首页

`<div class="navbar-header">`

`<a class="navbar-brand" href="index.html">Project name</a>`

`</div>`

---

3.这是副标题，用于网站分支题目

`<ul class="nav navbar-nav">`

`<li class="active"><a href="index.html">Home</a></li>`

`<li><a href="#">Link</a></li>`

`<li><a href="#">Link</a></li>`

`</ul>`

---

`</div>`

`</nav>`

`</header>`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 完成响应式导航条(创建三道杠按钮)

`<div class="navbar-header">`

1.navbar-toggle类用于应用CSS样式

2.数据类型data-toggle和data－targer是JS插件要用，分别表示预期行为和预期目标

3.icon-bar类是span用于创建按钮的三道杠按钮用的

`<button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">`

`<span class="icon-bar"></span>`

`<span class="icon-bar"></span>`

`<span class="icon-bar"></span>`

`</button>`

`<a class="navbar-brand" href="index.html">Project name</a>`

`</div>`

4.接下来把导航项(副标题)包装在一个手气的div中，即用带有适当Bootstrap类的div把<ul class="nav navbar-nav">包装起来:

`<div class="navbar-collapse collapse">`

5.此处的类navbar-collapse和collapse受上面(三道杠按钮)js控制

`<ul class="nav navbar-nav">`

`<li class="active"><a href="index.html">Home</a></li>`

`<li><a href="#">Link</a></li>`

`<li><a href="#">Link</a></li>`

`</ul>`
                    
`</div>`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 搭建传送带(旋转幻灯片)

1.原始代码如下:

`<img src="img/okwu.jpg" alt="OKWU.edu Homepage">`

`<img src="img/okwu-athletics.jpg" alt="OKWU Athletics Homepage">`

`<img src="img/bartlesvillecf.jpg" alt="Bartlesville Community Foundation">`

`<img src="img/emancipation.jpg" alt="Emancipation Stories">`

--- 

2.修改后代码如下:

`<div id="homepage-feature" class="carousel slide" >`

(整个传送带是一个带ID属性(id="homepage-feature"该属性可以自定义，但需注意和下面标签相一致)的div标签，其carousel类用于把bootstrap的传送带CSS应用到这个元素，为指示器、传送带项和前一张后一张控件添加样式)

3.创建进度指示器(下面小圈圈)

`<ol class="carousel-indicators">`

(进度显示器的data-target属性必须使用传送带的ID　homepage-feature)
(data-slide-to="0"从零开始)

`<li data-target="#homepage-feature" data-slide-to="0" class="active"></li>`

`<li data-target="#homepage-feature" data-slide-to="1"></li>`

`</ol>`

4.创建传送带项(即所有幻灯图片)

`<div class="carousel-inner">`

`<div class="item active">`

`<img src="img/okwu.jpg" alt="OKWU.edu Homepage">`

`</div>`

`<div class="item">`

`<img src="img/okwu-athletics.jpg" alt="OKWU Athletics Homepage">`

`</div>`

`</div>`

5.创建传送带控件(左右控件)

(每个传送带空间(carousel-controls)的href必须是最外围传送带的元素的ID值)

`<a class="left carousel-control" href="#homepage-feature" data-slide="prev">`

(此处用到Glyphicon字体图标)

`<span class="glyphicon glyphicon-chevron-left"></span>`

`</a>`

`<a class="right carousel-control" href="#homepage-feature" data-slide="next">`

`<span class="glyphicon glyphicon-chevron-right"></span>`

`</a>`

`</div>`

6.更改幻灯片切换时间

打开js/main.js文件，添加以下代码:

`$( document ).ready(function() {`

`$('.carousel').carousel({`

`interval: 2000 // 2 seconds vs. default 5`
	
`});`

`});`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 创建响应式分栏

col-12表示全宽
col-6表示半宽
col-4表示三分之一宽

Bootstrap内置的小屏幕断点恰好是768px,也就是@screen-sm-sim变量的默认值。而大于768px的中屏幕断点是992px，对应变量是@screen-md-min。然后大于1200px断点的算大屏幕。

1.container类用于约束内容的宽度，并使其在页面内居中;

->(总结:注意上述导航条也需添加container类)

`<div class="container">`

2.row类用于包装三个栏，并未栏间流出左右外边距;
(container和row类都设定了清除，因而他们可以包含浮动元素，同时又清除之前的浮动元素)

`<div class="row">`

`<div class="col-sm-4">`

`<h2>Welcome!</h2>`

`</div>`

`<div class="col-sm-4">`

`<h2>Recent Updates</h2>`

` </div>`

`<div class="col-sm-4">`

`<h2>Our Team</h2>`

`</div>`

`</div>`

`</div>`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 把链接`<a>`变成按钮

原代码如下:

`<p><a href="#">See our portfolio</a></p>`

更改后如下:

(btn类用于把链接变成按钮样式,btn-primary类用于把按钮编程主品牌颜色,pull-right类用于把链接浮动到右侧，使其占据更大空间，从而更便于发现和点击)

`<p><a href="#" class="btn btn-primary pull-right">See our portfolio</a></p>`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 根据需要定制Bootstrap的LESS文件

在工程中存在LESS文件,其内包含子文件__main.less和bootstrap文件夹
目录结构如下:

less

 `|`

_ __main.less

|

_bootstrap

     |

     _alerts.less

     |

     _bootstrap.less

     |

     _...

(**复制bootstrap.less文件，并新建文件，命名为__main.less**，它导入了其它所有文件，将来就是通过编译它来基于所有导入的LESS文件生成一个统一的样式表。**注意修改其内部文件路径:`@imoport "bootstrap/variabless.less"`**)

(添加__main.less文件的好处，就是可以独立创建自己的LESS文件，这样以来我们创建的文件不会于Bootstrap内置文件混淆，便于调整)

编译less:

如:　找到需要编译的less文件所在文件夹,输入**lessc __main.less > ../css/main.css**即可。

也可以使用sublime的插件less2css,该插件支持编译和错误信息提醒。

#### 要点总结:

1.在less文件下创建__main.less文件,复制粘贴bootstrap.less内容，但需要修改其中的@import链接目录地址。

2.选择需要更改的less模块文件，复制一份在less文件下，并修改名字(在其名字前加'_')，然后进行相关自定义修改，并保存。

3.记得在__main.less文件内添加覆盖之前的less模块文件，如(variable.less修改为_variable.less)。

4.编译__main.less生成main.css文件即可。

---

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 修改导航条样式

自定义变量,创建_variables.less文件，修改相关参数，如下:

// Basics of a navbar

`@navbar-height:                    64px;`(设置导航条高度)

`@navbar-margin-bottom:             0;`(设置导航条下边距)

`@navbar-default-color:             @gray;`(设置导航条默认颜色(即字体颜色))

`@navbar-default-bg:                #fff;`(设置导航条默认背景颜色)

`@navbar-default-border:            @gray-light;`(设置导航条边框颜色)

// Navbar links

`@navbar-default-link-color:                @navbar-default-border;`(设置链接默认颜色(即字体颜色))

`@navbar-default-link-hover-color:         @link-hover-color;`(设置链接hover时颜色)

`@navbar-default-link-hover-bg:             @off-white;`(设置链接hover时背景颜色)

`@navbar-default-link-active-color:         @link-hover-color;`(设置链接active激活时颜色)

`@navbar-default-link-active-bg:            @gray-lightest;`(设置链接active激活时背景颜色)

`@navbar-default-link-disabled-color:       @gray-lighter;`(??)

`@navbar-default-link-disabled-bg:          transparent;`(??)

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 导航条内添加LOGO

在html文件中找到:

`<a class="navbar-brand" href="index.html">这是网站名，也可以更改为网站LOGO图片</a>`

然后在`<a>`内添加`<img>`，注意要设置图片宽度width，否则图片会溢出

` <a class="navbar-brand" href="index.html"><img src="img/logo.png" alt="Bootstrappin" width="120"></a>`

后新建_navabar.less文件，修改.navbar-brand的padding值

`.navbar-brand {`

`/*   padding: @navbar-padding-vertical @navbar-padding-horizontal; */`

`padding: 22px 30px 0 15px;`

`}`

+ 调整导航项内边距，使文本和LOGO位于同一基线上

在_varbar.less中，找到.navbar_nav,

`@media (min-width: @grid-float-breakpoint) {`

`float: left;`

`margin: 0;`


`> li {`

`float: left;`

`> a {`

`//padding-top: ((@navbar-height - @line-height-computed) / 2);`

`//padding-bottom: ((@navbar-height - @line-height-computed) / 2);`

`padding: 30px 30px 14px;`

`font-size: 18px;`

`}`

`}`

`}`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

+ 添加导航图标(Glyphicons)

直接添加`<span class="glyphicon glyphicon-home"></span> `（记得人为跟字空一格）

建议弃用glyphicon的图标，使用font-awesome图标。

直接注释掉:__main.less内:

`//@import "bootstrap/glyphicons.less";`

+ 添加Font Awesome图标

官网下载

1.将其font文件内容全部复制至工程内font文件夹内

2.在less文件夹下创建font-awesome文件夹,并将官网下载了的Font Awesome的less文件下的全部内容，复制至此文件夹内

3.在__main.less文件内引用它:`//@import "font-awesome/font-awesome.less";`

4.确保`font-awesome/variables.less`内的`@fa-font-path`变量值是`:"../fonts"`;

5.编译__main.less即可

+ 调整导航项图标颜色

`.navbar-nav {`

`> li > a {`

/*修改导航条图标及字体*/

`color: @navbar-default-link-color;`

`.icon{//added rule set`

`color: @gray-light;`

`}`

/*修改鼠标hover和focus时的字体跟icon的字体颜色和背景颜色*/

`&:hover,`

`&:focus,`

`&:hover .icon,`

`&:focus .icon{`

`color: @navbar-default-link-hover-color;`

`background-color: @navbar-default-link-hover-bg;`

`}`

`}`

/*修改已被active了的链接，当鼠标hover和focus时的字体跟icon的字体颜色和背景颜色*/

`> .active > a {`

`&,`

`&:hover,`

`&:focus,`

`.icon, // added selector`

`&:hover .icon, // added selector`

`&:focus .icon { // added selector`

`color: @navbar-default-link-active-color;`

`background-color: @navbar-default-link-active-bg;`

`}`

`}`

+ 调整响应式导航条断点

因为在添加图片LOGO跟icon时，会增大了导航项,因为在视口介于768px和991px之间时，导航对于它的容器来说太宽了。@变量@grid-float-breakpoint决定了导航条在视口多宽的时候折叠起来，我们需要调整这个断点，以便在视口宽度达到下一个更宽的断点(@screen-md-min)之前，让导航条仍旧保持折叠。

在__variables.less中修改`@grid-float-breakpoint:@screen-sm-min`为`@grid-float-breakpoint:@screen-md-min`。

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!**自定义传送带样式**!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`>` 调整传送带

`>` 添加上下内边距

`>` 强制图片全宽

`>` 约束传送带的高度

`>` 重定位指示器

`>` 调整指示器外观

---

+ 调整传送带

1.复制carousel.less文件，并添加重命名为_carousel.less

2.把传送带两边的控件`<`和`>`改用font awesome图标，然后修养相关样式如下(_carousel.less):

`// Toggles`

`.icon-prev,`

`.icon-next,`

`.glyphicon-chevron-left,`

`.glyphicon-chevron-right ,`

`.icon{` //--------------added

`position: absolute;`

`top: 50%;`

`z-index: 5;`

`display: inline-block;`

`}`

`.icon-prev,`

`.glyphicon-chevron-left,`

`&.left .icon{`  //------------added

`left: 20%; ` //------eaited was 50%

`}`

`.icon-next,`

`.glyphicon-chevron-right,`//开始此处忘记添加逗号,发现没反应...

`&.right .icon{	`//表示串联选择器,.right和上面的.carousel-control都同属于一个标签，串联的好处是为了精准定位!!

`right: 20%; `//------eaited was 50%

`}`

+ 添加上下内边距(_carousel.less):

`// Wrapper for the slide container and indicators`

`.carousel {`

`position: relative;`

`padding-top: 4px;`

`padding-bottom: 28px;`

`background-color: @gray-lighter;`

`}`

+ 强制图片全宽(_carousel.less):

`.carousel-inner{`

`>.item{`

`>img,`

`>a>img{`

//强制图片全宽，在大屏情况下也能保持全宽

`min-width:100%;`//添加

`}`

`}`

`}`

+ 约束传送带的高度

`.carousel-inner{`

`...`

`>.item{`

`...`

`max-height:640px;`//新添加,限制图片高度，因为在中大屏中，传送带太高了，整体不显比例，所以添加此元素，超出部分会被overflow:hidden;

`>img,`

`>a>img{`

`...`

`@media (min-width: @screen-md-min) {`

`margin-top: -40px;`//调整屏幕过宽时，图片的垂直定位,为了图片能展示最中心部分

`}`

`@media (min-width: @screen-lg-min) {`

`margin-top: -60px;`//--------------------------------

`}`

`}`

`}`

`}`

+ 重定位指示器(_carousel.less):

需修改两处地方:

(一)为:

`.carousel-indicators {`

`position: absolute;`

`bottom: 0;`//此处修改编辑过

`margin-bottom: 0;`   //新添加元素

`...`

(二)为:

//在平板端或者更大屏幕端，其指示器位置也让其固定，所以把这里注释掉
  
`// Move up the indicators`

`// .carousel-indicators {`

`//   bottom: 20px;`

`//}`

+ 调整指示器外观(_carousel.less):

`.carousel-indicators {`

`...`

`li {`

`display: inline-block;`

`width:  16px;`//------修改指示器大小

`height: 16px;`//----修改指示器大小

//margin: 1px;//------

`background-color: @carousel-indicator-bg;`//-----添加背景颜色

`text-indent: -999px;`

`// border: 1px solid @carousel-indicator-border-color;`//去除边框
    
`border-radius: 10px;`
    
`cursor: pointer;`


// IE8-9 hack for event handling

`...`

`// background-color: #000 \9; // IE8`//---------------上面已经为元素添加背景颜色了，此处注释掉，否则产生干扰

`// background-color: rgba(0,0,0,0); // IE9`//----------------上面已经为元素添加背景颜色了，此处注释掉，否则产生干扰

`}`

`li:hover,`//----新添加

`.active {`

`// margin: 0;`//--去除active状态下的元素

`//width:  12px;`//--去除active状态下的元素

`//height: 12px;`//--去除active状态下的元素

`background-color: @carousel-indicator-active-bg;`//新添加

`}`

`}`

<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!**自定义分栏样式**!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->　

`>` 调整分栏极其内容

---

+ 调整分栏及其内容

#### (1.添加font图标，2.增加与传送带之间的间隔,3.三栏垂直并排时，添加之间间隔)

1.略

2.新建一个_pagecontens.less文件(用于添加额外的、更重要的响应式调整)

添加新属性:

`.page-contenss{`

`padding-top:20px;`

`padding-bottom:40px;`

`}`

然后在html文件中加入新属性:

`<div class="container page-contents">`

`<div class="row">`

3.

//

//次文件用于对页面相关元素的添加修改(切记元素名称不能跟bootstrap内的冲突)

//-------------------------------

`.page-contents{`  //添加内容于传送带之间的间隙

`padding-top: 20px;`

`padding-bottom: 40px;`
	 
/*

`[class*='col-']`

这个是正则的css
		
比如class*="col-"，表示所有css以col开始的都使用这个规则，
		
由于bootstrap里面很多cssname=col-xxx-xxx
		
所以这个css是为了定义所有col-xxx-xxx的规则的*/
	
`@media(max-width:@screen-xs-max){`
		
`[class*='col-']{`

`clear: both;`

`padding-bottom: 40px;`

`}`

`}`

`}`


<--!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!**自定义模块(页脚)**!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!-->

`>` 修饰页脚

---

+ 修饰页脚

#### (1.使用font图标替代文字，2.新建_footer.less，添加属性控制内容居中和调整font图标外观等)

`footer[role="contentinfo"] {`

`padding-top: 24px;`

`padding-bottom: 36px;`

`text-align: center;`

`}`

`ul.social {`

`margin: 0;`

`padding: 0;`

`width: 100%;`

`text-align: center;`

`> li {`

`display: inline-block;`

`> a {`

`display: inline-block;`

`font-size: 18px;`

`line-height: 30px;`

`.square(30px);`

`border-radius: 36px;`

`background-color: @gray-light;`

`color: #fff;`

`margin: 0 3px 3px 0;`

`&:hover {`

`text-decoration: none;`

`background-color: @link-hover-color;`

`}`

`}`

`}`

`}`
 
