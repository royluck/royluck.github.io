---
layout: post
title: CSS之margin/padding的重叠之谜
category: Studying
---

+ 在块级元素之间,它们之间的margin值会发生重叠=>假设上面的(top)块极为margin:20px;下面的块级(bottom)为margin:20px;按照正常思维来想,其二者之间的上下间隔应该是:20px+20px=40px;而实际上它们会发生重叠,其上下间隔却是20px.

}
`.right img
{
	margin: 20px;
	**display: block;**(转化为块级元素,因为img为行内元素)
	border: 1px solid #000;
}`

+ 父元素存在padding值，其子元素存在margin值，则父元素的padding值会和margin重叠。

[查看demo](http://royluck.github.io/demo/task10/) （==>删除box1内的元素`margin:20px 0px;`会发现没有改变，因为其和`padding:20px;`重叠）
