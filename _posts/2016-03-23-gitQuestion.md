---
layout: post
title: Git问题汇总
category: Studying
---

#### 远程库推送不成功

+ 其原因很有可能在首次跟远程库建立链接时,在输入`git remote add origin git@github.com:royluck/远程库名.git`时,把远程库名字打错.解决方法是:打开工作区,找到隐藏的.git文件,打开config配置文件,在url:行内正确输入文件名地址,即可.
