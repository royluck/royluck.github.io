---
layout: post
title: CSS之margin的重叠之谜
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
