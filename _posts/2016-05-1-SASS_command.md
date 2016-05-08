---
layout: post
title: SASS之命令汇总
category: Studying
---

+ 更新Sass

`gem update sass`

---

+ 卸载（删除）Sass

`gem uninstall sass`

---

+ 终端编译输出并随时检测CSS文件命令

`sass --watch  XXX.scss:XXX.css`

在编译的时候带上参数“--style expanded”以展开的方式输出CSS格式

`sass --watch test.scss:test.css  --style expanded`

---

+ `!default` 表示默认值

sass 的默认变量一般是用来设置默认值，然后根据需求来覆盖的，覆盖的方式也很简单，只需要在默认变量之前重新声明下变量即可。

`$btn-primary-color : #fff !default;`

+ 当在局部范围（选择器内、函数内、混合宏内...）声明一个已经存在于全局范围内的变量时，局部变量就成为了全局变量的影子。基本上，局部变量只会在局部范围内覆盖全局变量。

+ .scss和.sass文件相互转换

`sass-conver main.scss main.sass`（两者书写方式不同)

+ 定义变量(通过`$`声明变量)

如`$headline-ff:宋体;`


+ 类的嵌套，在生成的css中，其类之间是以空格隔开，所以在使用伪属性(如`：after :hover`等)时,需注意！在其前加**&**

如：

`a{`

`@:hover{`

`color:red;`

`}`

`}`

否则：

其生成的css内容为:

`a :hover{...}` 其内容相当于`a *:hover{...}`(a标签里面的所有元素都添加hover属性)

+ sass不仅支持类嵌套还支持属性嵌套(**属性嵌套记得加冒号:**)

如:

`.headline{`

`font:{`

`family:宋体;`

`size:14px;`

`}`

`}`

其生成css内容为:

`.headline{font-family:宋体;font-size:14px;}`

+ `mixin`　函数(可以直接在scss主文件声明,也可以单独创建一个文件用来专门存储mixin内容)

=>新建一个scss文件为：_mixin.scss,输入以下内容

`@mixin col-6(){`

`width:50%;`

`float:left;`

`}`

=>在scss主文件里面调用

先引入上述文件:`@import "mixin";`

调用它:

`.webdemo-sec{`

`@include col-6();`

`}`

+ mixin函数传参

`@mixin col($width:50%){`//调用时不输入传参值时，其默认值为50%

`width:$width;`

`}`

==>调用

`.webdemo{`

`@include col(25%);`

`}`

+ 继承样式@extend

==>输入内容

`.error{`

`color:#f00;`

`}`

`.serious-error{`

`@extend .error;`//继承上面.error样式

`border:1px solid #f00;`

`}`

==>生成效果

`.error , .serious-error{`

`color:#f00;`

`}`

`.serious-error{`

`border:1px solid #f00;`

`}`

+ @extend两个知识点

1.`@extend`不能继承选择器序列

如：

`.A .B{`

`color:#f00;`

`}`

`.c{`

`@extend .A .B;`//此时生成的css文件会报错!

`}`

2.使用%,用来构建只用来继承的选择器，避免代码冗余;

`%error{`

`color:#f00;`

`}`

`.serious-error{`

`@extend %error;`

`}`

+ 在嵌套的时候，使用@at-roof指令

`.main-sec{`

`font-family:$main-sec-ff;`

`@at-roof{`

`.main-sec-headline{`

`family:$main-sec-ff;`

`size:16px;`

`}`

`}`

`}`

+ 移动互联网(响应式布局)

#### media

sass中的media query可以内嵌在css规则中，在生成css的时候，media query才会被提到样式的最高层级。其好处是:避免了重复书写选择器或者打乱样式表的流程

`@mixin col-sm($width:50%){`

`@media(min-width:768px){`//生成css样式表时，media会被提到样式表最外层

`width:$width;`

`float:left;`

`}`

`}`

调用:

`.webdemo-sec{`

`@include col-sm();`

`}`

生成:

`@media(min-width:768px){`//media会被提到样式表最外层

`.webdemo-sec{`

`width:50%;`

`float:left;`

`}`

`}`

+ mixin函数的判断!!

参考代码:

`@mixin col-sm($width:50%){`

`@if type-of($width)!=number{`

`@error "$width必须是一个数值类型，你输入的width是: #{$width}.";`

`}`

`@if not unitless($width){`

`@if unit($width)!="%"{`

`@error "$width应该是一个百分值,你输入的width是:　#{$width}.";`

`}`

`}@else {`

`@warn "$width应该是一个百分值,你输入的width是:　#{$width}.";`

`$width:(percentage($width)/100);`//此处需加除100，是因为其默认生成值会增加100倍

`}`

`@media(min-width:768px){`

`width:$width;`

`float:left;`

`}`

`}`

