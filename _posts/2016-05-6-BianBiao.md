---
layout: post
title: JS的作用域和闭包
category: Studying
---

+ 闭包的应用：

1.闭包就是能够读取其他函数内部变量的函数。

2.让这些变量的值始终保持在内存中。

3.闭包可以保护函数内的变量安全。

`function a(){`

`var i = o;`

`function b(){`

`alert(++i);`

`}`

`return b;`

`}`


var c = a();
c();
