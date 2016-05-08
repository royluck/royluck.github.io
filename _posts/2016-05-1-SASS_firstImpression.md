---
layout: post
title: SASS之爱的初体验
category: Studying
---

+ SASS是CSS的超集

+ SASS和CSS区别

Sass和CSS写法的确存在一定的差异，由于 Sass 是基于 Ruby 写出来，所以其延续了 Ruby 的书写规范。在书写 Sass 时不带有大括号和分号，其主要是依靠严格的缩进方式来控制的。

---

+ SCSS和CSS写法无差别：

SCSS和CSS写法无差别，这也是 Sass 后来越来越受大众喜欢原因之一。简单点说，把你现有的“.css”文件直接修改成“.scss”即可使用。

---

+ Sass 的编译有多种方法：

[命令编译](http://www.imooc.com/code/6378)

(终端编译SASS文件命令：`sass --watch  XXX.scss:XXX.css`)

GUI工具编译

自动化编译

---

+ 常见的编译错误

而最为常见的一个错误就是字符编译引起的。在Sass的编译的过程中，是不是支持“GBK”编码的。所以在创建 Sass 文件时，就需要将文件编码设置为“utf-8”。

另外一个错误就是路径中的中文字符引起的。建议在项目中文件命名或者文件目录命名不要使用中文字符。而至于人为失误造成的编译失败，在编译过程中都会有具体的说明，大家可以根据编译器提供的错误信息进行对应的修改。

---

+ 不同样式风格的输出方法

#### 嵌套输出方式 expanded

在编译的时候带上参数“ ` --style expanded`”:

`sass --watch test.scss:test.css  --style expanded`

![](http://img.mukewang.com/54f54e2c0001c2c004850281.jpg)

![](http://img.mukewang.com/54f54dab00019a0504880296.jpg)

![](http://img.mukewang.com/54f7b4bb00014f9908020299.jpg)

![](http://img.mukewang.com/54f5511d0001b5c206660401.jpg)

---

+ 响应调试

#### 谷歌浏览器调试：

step1:F12打开调试面板，点击调试面板右上角的齿轮图标打开设置，在general选项中勾选Enable CSS source map 和 Auto-reload generated CSS。

step2:找到.scss源文件，在浏览器修改.scss内容，右击save或ctrl+s即可

---

###　实例

+ 创建一个sass文件

mkdir learn-sass-cli

+ 进入该文件

cd learn-sass-cli

+ 在该文件下新建一个scss文件

+ 编译scss文件生成css文件

sass main.scss main.css

+ 编译的同时，会生成.map文件，该文件用来映射.scss文件和css文件

---

+ 变量操作

1.直接操作变量，即变量表达式。

2.通过函数

-跟代码块无关的函数，多是自己内置函数，称functions.

-可重用的代码快，称`mixin`(类似C语言的宏)

->@include的方式调用(复制拷贝方式)

->@extend的方式调用(一组合声明形式存在)

---

+ extend两个知识点

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

+ 移动互联网(响应式布局)

#### media

media query

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
