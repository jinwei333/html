HTML 标签

|     标签      | 描述                                                         |                                  |
| :-----------: | ------------------------------------------------------------ | -------------------------------- |
|    \<html>    | 定义 HTML 文档                                               |                                  |
|    \<body>    | 定义文档的主体                                               | aaaaaaa                          |
|     \<h1>     | 定义 HTML 标题。1到6号标题与1到6号字体逆序对应，比如1号字体对应6号标题，2号字体对应5号标题。 |                                  |
|     \<hr>     | 定义水平线                                                   |                                  |
|   \<!-- -->   | 定义注释                                                     |                                  |
|     \<p>      | 定义一个段落                                                 |                                  |
|     \<br>     | 不产生一个新段落的情况下进行换行（新行）                     |                                  |
|     \<b>      | 定义粗体文本                                                 |                                  |
|     \<em>     | (emphasize)，定义着重文字                                    |                                  |
|     \<i>      | （italic），定义斜体字                                       |                                  |
|   \<small>    | 定义小号字                                                   |                                  |
|   \<strong>   | 定义加重语气                                                 |                                  |
|    \<sub>     | （subscript）定义下标                                        |                                  |
|    \<sup>     | (superscript) 定义上标                                       |                                  |
|    \<ins>     | (insert) 定义插入字                                          |                                  |
|    \<del>     | (delete) 定义删除字                                          |                                  |
|    \<code>    | 定义计算机代码                                               |                                  |
|    \<kbd>     | (keyboard) 定义键盘吗                                        |                                  |
|    \<var>     | 定义变量                                                     |                                  |
|    \<pre>     | 定义预格式文本。使用 pre 标签对空行和空格进行控制。所见即所得 |                                  |
|    \<abbr>    | 定义缩写                                                     |                                  |
|  \<address>   | 定义地址                                                     |                                  |
|    \<abbr>    | 全词缩写 \<abbr title="etcetera">ect.\</abbr>                |                                  |
|  \<acronym>   | 表示标记一个首字母缩写。 \<acronym title="World Width Web">WWW\</acronym>。在某些浏览器中，当您把鼠标移至缩略词语上时，title可用于展示表达的完整版本。 |                                  |
|    \<bdo>     | (Bi-Directional Override)定义文字方向。 \<bdo dir="rtl">我爱你\</bdo> |                                  |
| \<blockquote> | 定义长的引用                                                 |                                  |
|     \<q>      | (quate) 定义短的引用语                                       |                                  |
|    \<cite>    | 定义引用，论证                                               |                                  |
|     \<a>      | 设置超文本链接。                                             | <a href="www.baidu,com">百度</a> |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |
|               |                                                              |                                  |



#### 网址链接

\<a href="www.baidu.com">访问百度</a>	效果为： <a href="www.baidu.com">访问百度</a>

> **提示:** *"链接文本"* 不必一定是文本。图片或其他 HTML 元素都可以成为链接。

\<a href="www.baidu.com” target="C4" rel="noopener noreferrer">访问菜鸟教程!\</a>

**target** 属性，定义被链接的文档在何处显示。、

"_blank"： 浏览器总在一个新打开、未命名的窗口中载入目标文档。

“_parent” 这个目标使得文档载入父窗口或者包含来超链接引用的框架的框架集。如果这个引用是在窗口或者在顶级框架中，那么它与目标 _self 等效。

“_self” 个目标的值对所有没有指定目标的 <a> 标签是默认目标，它使得目标文档载入并显示在相同的框架或者窗口中作为源文档。这个目标是多余且不必要的，除非和文档标题 <base> 标签中的 target 属性一起使用。

“_top” 这个目标使得文档载入包含这个超链接的窗口，用 _top 目标将会清除所有被包含的框架并将文档载入整个浏览器窗口。

**id** 属性，用于创建在一个HTML文档书签标记。

示例：

```html
<a href="www.baidu.com">访问百度</a>	<!-- 定义一个链接 -->
<a id = "tips">有用的提示部分</a>		<!-- HTML文档中插入id -->
<a href="#tips">访问有用的提示部分</a>	<!-- HTML文档中创建一个链接到"id=tips" -->
<a href="www.abcd.com#tips">访问有用的部分</a> <!-- 从另一个页面创建一个链接到"有用的提示部分 -->
```

#### 图片链接

\<img src=".\img\test.jpeg" border="10" width="300" height="150">

border: 是否带边框

#### 发送邮件

```html
<a href="mailto:1343711279@qq.com?bcc=1016064427@qq.com&subject=Eating&body:I want to eat fruit" rel="nofollow">发送秘密文件</a>
```

| 参数                    | 描述             |
| ----------------------- | ---------------- |
| mailto:*name@email.com* | 邮件接收地址     |
| cc=*name@email.com*     | 抄送地址         |
| bcc=*name@email.com*    | 密件抄送地址     |
| subject=*subject text*  | 邮件主题         |
| body=*body text*        | 邮件内容         |
| ?                       | 第一个参数分隔符 |
| &                       | 其他参数分隔符   |

**抄送：**

英文名称：Carbon Copy，又简称为 CC。在网络术语中，抄送就是将邮件同时发送给收信人以外的人，用户所写的邮件抄送一份给别人，对方可以看见该用户的 E-mail。同收件人地址栏一样，不可以超过 1024 个字符。一般来说，使用"抄送"服务时，多人抄送的电子邮件地址使用 **;** 分隔。

**密件抄送：**

英文名称：Blind Carbon Copy ，又称“盲抄送”，和抄送的唯一区别就是它能够让各个收件人无法查看到这封邮件同时还发送给了哪些人。密件抄送是个很实用的功能，假如一次向成百上千位收件人发送邮件，最好采用密件抄送方式，这样一来可以保护各个收件人的地址不被其他人轻易获得，二来可以使收件人节省下收取大量抄送的 E-mail 地址的时间。



#### HTML head

**\<head>** 元素包含了所有的头部标签元素。在 \<head>元素中你可以插入脚本（scripts）, 样式文件（CSS），及各种meta信息。

可以添加在头部区域的元素标签为: \<title>, \<style>, \<meta>, \<link>, \<script>, \<noscript> 和 \<base>。

> 注意 head 不同于 header 标签用于定义文档的页眉

**\<title>** 标签定义了不同文档的标题。

\<title> 在 HTML/XHTML 文档中是必须的。

\<title> 元素:

- 定义了浏览器工具栏的标题
- 当网页添加到收藏夹时，显示在收藏夹中的标题
- 显示在搜索引擎结果页面的标题

```html
<html>
<head>
    <meta charset="utf-8">
    <title>文档标题</title
</head>
</html>
```

**\<base>** 定义页面中所有链接默认的链接目标地址。

```html
<base href="." target="_blank">
```

**\<meta>** 描述HTML文档的描述，关键词，作者，字符集等。

```html
<meta name="keywords" content="HTML, CSS, XML, JavaScript">	<!-- 为搜索引擎定义关键词 -->
<meta name="description" content="Must to learn!!!">		<!-- 为网页定义描述内容 -->
<meta name="author" content="King">	<!-- 定义网页作者 -->
<meta http-equiv="refresh" content="30">	<!-- 每30秒刷新当前页面 -->
```



**\<link>** 定义了文档与外部资源之间的关系。通常用于链接到样式表。

```html
<link rel="stylesheet" type="text/css" href="mystyle.css">
```

**\<style>** 定义了HTML文档的样式文件引用地址。在\<style> 元素中也可以直接添加样式来渲染 HTML 文档.

**\<script>** 定义客户端的脚步文件



## CSS

#### css 的使用

CSS 是在 HTML 4 开始使用的,是为了更好的渲染HTML元素而引入的.

CSS 可以通过以下方式添加到HTML中:

- 内联样式- 在HTML元素中使用"style" **属性**。
- 内部样式表 -在HTML文档头部 \<head> 区域使用\<style> **元素** 来包含CSS。
- 外部引用 - 使用外部 CSS **文件**。

好的方式是通过外部引用CSS文件。

```html
<html>
<head>
	<meta charset="utf-8">
	<title>CSS样式</title>
	<style type="text/css">	<!-- 内部样式表 -->
		h1 {color: red;}
		p {color: blue;}
	</style>
	<link rel="stylesheet" type="text/css" href="style.css">	<!-- 外部样式表 -->
</head>
<body style="background-color: gray;">	<!-- 内联样式表 -->
	<h1 style="font-family: 隶书; text-align: center; font-size: 100px;">标题1</h1>
	<p style="color: green; background-color: pink ;margin-left: 50px;">段落1</p>

	<h2 style="background-color: black; color: white;">标题2</h2>
	<p style="background-color: green; color: black;">段落2</p>
</body>
</html>
```

### 图像

定义图像的格式：**\<img src="url" alt="some_text" width=“300” height=“200”>**

alt 属性用来为图像定义一串预备的可替换的文本。在浏览器无法载入图像时，替换文本属性告诉读者她们失去的信息。

> **提示:** 指定图像的高度和宽度是一个很好的习惯。如果图像指定了高度宽度，页面加载时就会保留指定的尺寸。如果没有指定图片的大小，加载页面时有可能会破坏HTML页面的整体布局。

\<span> 用于对文档中的行内元素进行组合。

\<span> 标签没有固定的格式表现。当对它应用样式时，它才会产生视觉上的变化。如果不对 <span> 应用样式，那么 <span> 元素中的文本与其他文本不会任何视觉上的差异。

\<span> 标签提供了一种将文本的一部分或者文档的一部分独立出来的方式。

\<div> 标签定义 HTML 文档中的一个分隔区块或者一个区域部分。

\<div>标签常用于组合块级元素，以便通过 CSS 来对这些元素进行格式化。

## HTML \<script> 标签

\<script> 标签用于定义客户端脚本，比如 JavaScript。

\<script> 元素既可包含脚本语句，也可通过 src 属性指向外部脚本文件。

JavaScript 最常用于图片操作、表单验证以及内容动态更新。

## HTML\<noscript> 标签

\<noscript> 标签提供无法使用脚本时的替代内容，比方在浏览器禁用脚本时，或浏览器不支持客户端脚本时。

\<noscript>元素可包含普通 HTML 页面的 body 元素中能够找到的所有元素。

只有在浏览器不支持脚本或者禁用脚本时，才会显示 \<noscript> 元素中的内容：



# HTML 统一资源定位器(Uniform Resource Locators)

------

URL 是一个网页地址。

URL可以由字母组成，如"runoob.com"，或互联网协议（IP）地址： 192.68.20.50。大多数人进入网站使用网站域名来访问，因为 名字比数字更容易记住。





[HTML5](http://lib.csdn.net/base/html5)中引入新的元素canvas，其drawImage 方法允许在 canvas 中插入其他图像( img 和 canvas 元素) 。drawImage函数有三种函数原型：

> drawImage(image, dx, dy) 
> drawImage(image, dx, dy, dw, dh) 
> drawImage(image, sx, sy, sw, sh, dx, dy, dw, dh)

第一个参数image可以用HTMLImageElement，HTMLCanvasElement或者HTMLVideoElement作为参数。dx和dy是image在canvas中定位的坐标值；dw和dh是image在canvas中即将绘制区域（相对dx和dy坐标的偏移量）的宽度和高度值；sx和sy是image所要绘制的起始位置，sw和sh是image所要绘制区域（相对image的sx和sy坐标的偏移量）的宽度和高度值。

![](D:\HTML\2020-11-03\img\0_1312439694SFqd.gif)



在画圆的时候，使用下面的方法

**arc(x,y,r,start,stop)**

画布的左上角坐标为 0, 0

-  x：圆心在x轴上的坐标
-  y：圆心在y轴上的坐标
-  r：半径长度
-  start：起始角度，以弧度表示，圆心平行的右端为0度
-  stop：结束角度，以弧度表示

注意：Math.PI表示180°，画圆的方向是顺时针

创建线性渐变时 **context.createLinearGradient(x,y,x1,y1)** 括号内的参数含义如下：

-  **x**: 起始位置的x坐标
-  **y**: 起始位置的y坐标
-  **x1**: 渐变终点位置的x坐标
-  **y1**: 渐变终点位置的y坐标

制作径向渐变时 **context.createRadialGradient(x , y , r , x1 , y1 , r1)** 括号内参数含义如下:

-  x: 渐变的开始圆的 x 坐标
-  y: 渐变的开始圆的 y 坐标
-  r: 开始圆的半径
-  x1: 渐变的结束圆的 x 坐标
-  y1: 渐变的结束圆的 y 坐标
-  r1: 结束圆的半径

(x, y, r) (x1,y1,r1)分别可以代表一个圆形的特征, 个人感觉通常情况下(x,y) 和 (x1,y1)简单地相同即可(即同心圆), 这样做出来的径向渐变已经十分美观,符合大众审美观。