---
layout: post
title: H5BP模板改造为Bootstrap模板过程
category: Studying
---

+ 删除的文件

1.因为我们要利用LESS创建自己的CSS文件，所以要删除CSS文件夹.

2.CHANGELOG.md

3.CONTRIBUTING.md

4.doc文件夹及其内容

5..htaccess文件

+ 剩余文件其作用介绍:

1.human,txt:这个文件记载贡献者,H5BP、Bootstrap的，还有其它贡献者

2.LICENSE.md:在H5BP许可前面，加上你基于该许可构建的网站的许可信息，在H5BP许可之后，加上Bootstrap以及其它站点中用到的重要的库的许可信息。

3.README.md:跟新这个文件，加上自己项目的说明信息.

+ 添加Bootstrap文件:

1.fonts文件(并添加.htaccess文件(具体看书P224))

2.在js文件夹下再创建一个名为bootstrap文件夹，并把bootstrap的js文件夹中的脚本文件都复制过来.
把Bootstrap原文件内的bootstrap.min.js文件内的全部代码复制粘贴到文件夹中的plugin.js内.

3.Bootstrap内的LESS文件.

4.新建CSS文件夹
