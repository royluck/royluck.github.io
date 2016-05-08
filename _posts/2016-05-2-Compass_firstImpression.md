---
layout: post
title: Compass之爱的初体验
category: Studying
---

Compass is an open-source CSS Authoring Framework.（CSS开源书写框架）

---

**利用Compass和现有的前端集成化解决方案整合**

---

### 实例:

+ `mkdir workspace`

+ `cd workspace`

+ 创建compass项目

`compass create learn-compass-init`(创建的项目名)

+ cd learn-compass-init

---

+ ls

==>`config.rb`:配置文件

==>`sass`:为sass文件的存储目录

==>`stylesheet`:为css编译输出的存储目录

#### ==>cd sass

框架

`ie.scss:`

`print.scss:`

`screen.scss:`

#### ==>cd stylesheet

`ie.css`

`ptint.css`

`screen.css`

#### ==>config.rb

配置格式书写如下：

`http_path = "/"`

`css_dir = "stylesheets"`CSS输出目录

`sass_dir = "sass"` SASS目录

`images_dir = "iamges"`图片木库

`javascript_dir = "javascript"`JS目录

---

+ 为了让文件实时编译，来监视compass文件的变化

`compass watch`

+ 把常见变量抽离存储在一个专门的文件里面

在sass文件夹里面新建一个文件_variable.scss(文件名字加前缀下划线_，表示局部文件，因为该文件不用生成css文件！)

+ 在screen.scss(宿主文件)文件里面引用_variable.scss文件，把它包含进去

`@import "variables";`(记得区分，和css里的import指令，两者不一样)

注：`@impor "compass.reset";`把默认样式全部重置归零(可用插件:Normalize解决它的弊端)

+ 如果想用css原生@import时，可通过以下规则：

![见图片ipad]()

+ 基于sass的既定规则：

1. 没有文件后缀名的时候,sass会内部自动查找添加.scss或.sass的后缀(如上述`@impot "variable";`)

2. 同一目录下,局部文件和非局部文件不能重名(如_variables.scss和variables.scss)

+ scss文件可以用/**/和//注释，但前者能输出到编译出来的css文件当中，而后者//不行

+ (编译?)

`compass compile`




