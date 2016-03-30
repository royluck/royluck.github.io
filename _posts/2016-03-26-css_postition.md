---
layout: post
title: CSS之垂直水平居中(含broder-radiu属性理解)
category: Studying
---

+ 如果父级元素是绝对定位（absolute）或者没有设置，里面的绝对定位（absolute）自动以body定位。这句话是错的。
**正确的是：只要父级元素设了position并且不是static（默认既是static），那么设定了absolute的子元素即以此为包含块（最近的）。**
绝对定位（Absolute positioning）元素定位的参照物是其包含块，既相对于其包含块进行定位，不一定是其父元素。

`.main
{
	width: 400px;
	height: 200px;
	background: #ccc;
	position: absolute; top:50%;left: 50%;
	margin-left: -200px;
	margin-top: -100px;

}`

如上代码:假设其宽度width为400px;高度height为200px;当使用绝对定位`position:absolute`,此时`.main`相对`body`定(因为`.main`不存在父级元素).其定位值为=>`top:50%;left:50%`;但此时观察,`.main`并不是绝对水平居中,因为left和top只是块的**边**距离body边界的距离,此时需要通过`margin-left:-200px;`(.main宽度为400px)和`margin-top:-100px;`(.main高度为200px)移动,使其**.main的参考点移至.main的中心.**

+ broder-radius(值1 值2 值3 值4);

如:broder-radius(0 0 0 100%);=>其效果为左下部分圆.
