XML概念

## 1.什么是XML

XML是可扩展的标记性语言。

以下是一段标准的XML数据格式：

<img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713133812.png" style="zoom:50%;" />

XML 数据格式最主要的功能：数据传输

<img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713134213.png" style="zoom:80%;" />

XML是指：可扩展性标记语言

XML 被发明的目的：传输和存储数据，而不是展示数据（HTML是用来展示数据的）

XML 的标签必须自定义，但是在写标签名的时候一定要有含义

XML 是 W3C推举的数据传输格式；

XML 的主要作用：

	1. 用来保存数据，而且这些数据具有自我描述性质=
	2. 它可以做为项目或者模块的配置文件
	3. 还可以作为网络传输数据的格式（现在 JSON 为主）。

## 2.如何编写一个XML文件

<img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713135027.png" style="zoom:80%;" />

Test.XML 是文件名

<root></root> 为根节点 

注意：

每一个XML文件必须有一个根节点(可以自己随意定义)，必须包含所有的XML代码，相当于HTML中的html根节点。

## 3.XML和HTML的区别

- HTML 标签不能自定义，XML 标签只能自定义
- HTML 语法要求不严格，XML 语法要求严格，必须是成对标签
- HTML 用于展示数据，HTML 用来传输和存储数据



## 4.XML的基本语法

### 4.1 语法规则

- 标签中的标签名是自定义的，可以是汉语，也可以是英语

- 标签名中不能出现空格

- XML 中的元素（标签）可以使用单标签和双标签

  单标签 ：

    格式：<标签名 属性=“值” 属性=“值” ... />

  双标签：

    格式：<标签名 属性=“值” 属性=“值”...>文本数据或子标签</标签名>

- XML 所有标签都要闭合

- XML必须有根节点，根节点就是其他所有节点的父级节点。没有父标签的元素，叫做顶级元素。根元素是没有父标签的顶级元素，而且有且只有一个。

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713140147.png" style="zoom: 80%;" />

  此文档中的根节点就是 ： root

- XML 头声明：可有可无，建议书写

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713140513.png" style="zoom:80%;" />

  version 是版本号，encoding是编码格式

- XML 所有 XML 元素必须是成对标签

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713140801.png" style="zoom:80%;" />

- 标签名大小写敏感（标签区分大小写）

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713140947.png" style="zoom:80%;" />

- 标签不能交叉

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713141231.png" style="zoom:80%;" />

- XML 中的注释和 HTML的注释一样

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713141414.png" style="zoom:80%;" />

- 特殊字符使用实体字符转义

  $lt 相当于 <

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713142416.png" style="zoom:50%;" />

  <img src="../../../../AppData/Roaming/Typora/typora-user-images/image-20210713142218626.png" alt="image-20210713142218626" style="zoom: 50%;" />

### 4.2 元素的属性

- 一个标签可以有多个属性，属性的值必须使用单引号或者双引号引起来。

- 命名规则：数字 、字母、下划线。开头不能为数字

- 属性就是表示标签自身的一些额外信息

- 在解析 XML 的时候，属性会带来额外的解析代码（多了一步，比较麻烦）

  <img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713143420.png" style="zoom:50%;" />

  这里的 age 就是一个属性

## 5.CDATA

CDATA语法可以告诉 xml解析器，我的里面的文本内容，只是纯文本，不需要 xml 语法解析。

语法格式：

> <![CDATA[...不解析的内容...]]>

CDATA 区内容不解析，直接进行输出。

<img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713145123.png" style="zoom:50%;" />

注意：特使字符较少时，使用实体替换，特殊字符较多时，使用CDATA区域，CDTAT必须大写。

## 6.XML的解析技术

- 不管是 html 文件还是 xml 文件他们都是标记型文档，都可以使用 W3C 组织制定的 dom 技术来解析。（就是将每一个标签都当做一个dom对象处理）

- dom技术：文档对象模型（DOM）是表示文档（比如HTML和XML）和访问、操作构成文档的各种元素的应用程序接口（API）,w3c DOM，是指W3C定义的标准的文档对象模型，它以树形结构表示HTML和XML文档，定义了遍历这个树和检查、修改树的节点的方法和属性。

<img src="https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713154537.png" style="zoom: 67%;" />

- document 对象表示的是整个文档（可以是 html ，也可以是 xml）

![](https://gitee.com/YunboCheng/imageBad/raw/master/image/20210713163325.png)


