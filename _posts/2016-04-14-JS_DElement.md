---
layout: post
title: JS-DOM Element对象
category: Studying
---

---

+ removeAttribute() 方法删除指定的属性。

参考代码：

`if(this.value.length>5){`

`aEm[1].className="active";`

`pwd2.removeAttribute("disabled");`

`pwd2_msg.style.display="block";`

`}`

`else {`

`aEm[1].className="";`

`pwd2_msg.style.display="none";`

`pwd2.setAttribute("disabled","");`

}

+ setAttribute() 方法添加指定的属性，并为其赋指定的值。

参考代码：

`if(this.value.length>5){`

`aEm[1].className="active";`

`pwd2.removeAttribute("disabled");`

`pwd2_msg.style.display="block";`

`}`

`else {`

`aEm[1].className="";`

`pwd2_msg.style.display="none";`

`pwd2.setAttribute("disabled","");`

}

**注：**.setAttribute( , );的参数是两个，只写一个是不可以的，removeAttribute可以写一个，正确写法为pwd2.setAttribute("disabled","");


