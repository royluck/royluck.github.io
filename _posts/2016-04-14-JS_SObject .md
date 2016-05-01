---
layout: post
title: JS-String 对象
category: Studying
---

+ charAt() 方法可返回指定位置的字符。

参考代码：（判断字符是否一样）

`function findStr(str,n){`

`var tmp=0;`

`for(var i=0;i<str.length;i++){`

`if(str.charAt(i)==n){`

`tmp++;`

`}`

`}`

`return tmp;`

`}`

+ replace() 方法用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串。

参考代码：（一个汉字等于两个字符，计算字符串字数）

`function getLength(str){`

`return str.replace(/[^\x00-xff]/g,"xx").length;`

`}`
