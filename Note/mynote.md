---
typora-root-url: img
---



# float

 float 被设计的初衷：文字环绕效果。



### 包裹性

> float为什么要具有包裹性？其实答案还得从float的设计初衷来寻找，float是被设计用于实现文字环绕效果的。文字环绕图片比较好理解，但是如果想要让文字环绕一个div呢？此时div不被“包裹”起来，那么如何去实现环绕效果？

### 清空格

> “清空格”这一特性的根本原因是由于float会导致节点脱离文档流结构。它都不属于文档流结构了，那么它身边的什么换行、空格就都和它没关系的，它就尽量的往一边去靠拢，能靠多近就靠多近，这就是清空格的本质。

### 清除 float

1. 为父元素添加overflow:hidden
2. 浮动父元素
3. 浮动元素下方添加一个 clear:both 的元素，可以消除float的破坏性。
4. clearfix： 定义一个.clearfix类，然后对float元素的父元素应用这一样式即可



# display


<img src="https://images0.cnblogs.com/blog2015/138012/201503/060814397278889.png" alt="img"  />



1. list-item：通过它可以模拟li列表样式；
2. table：也是一个“块”，但和block相比，table具有包裹性；
3. table-cell：最新的多列布局解决方案；

常用的有 **none inline block inline-block** 

## inline 

可以把 inline 元素想象成一个杯子里的水，它是“流”，是没有大小和形状的，它的宽度取决于父容器的宽度。

inline 行内元素: `<span> <img> <a>`

1. 使元素变成行内元素，拥有行内元素的特性，即可以与其他行内元素共享一行，不会独占一行。
2. 不能更改元素的height，width的值，大小由内容撑开。
3. 可以使用padding上下左右都有效，margin 只有 left 和 right 产生边距效果，但是top和bottom就不行。

## block

`<div> <h> <p> <ul>` 

1. 使元素变成块级元素，独占一行，在不设置自己的宽度的情况下，块级元素会默认填满父级元素的宽度。
2. 能够改变元素的height，width的值。
3. 可以设置padding，margin的各个属性值，top，left，bottom，right都能够产生边距效果。

## inline-block 

`<button> <select> <textarea> <input> <object>`

1. 结合了inline与block的一些特点，结合了上述inline的第1个特点和block的第2,3个特点。
2. 用通俗的话讲，就是不独占一行的块级元素。

# position

[https://www.cnblogs.com/wangfupeng1988/p/4322680.html](https://www.cnblogs.com/wangfupeng1988/p/4322680.html)

| 定位模式 | 是否脱标             | 是否可以边偏移 | 移动位置基准       |
| -------- | -------------------- | -------------- | ------------------ |
| static   | 否，正常模式         | 不可以         | 正常模式           |
| relative | 脱标，占有位置       | 可以           | 相对于自身位移     |
| absolute | 完全脱标，不占有位置 | 可以           | 相对父/祖移动      |
| fixed    | 完全脱标，不占有位置 | 可以           | 相对浏览器移动位置 |

## 1. relative

relative会导致自身位置的相对变化，而不会影响其他元素的位置、大小的变化。

坐标参考，固定元素左上为原点。

![image-20210313220626976](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210313220626976.png)



## 2. absolute

**根据最近的定位上下文确定位置：**

浏览器会递归查找该元素的所有父元素，如果找到一个设置了position:relative/absolute/fixed的元素，就以该元素为基准定位，如果没找到，就以浏览器边界定位。



<img src="/absolute1.png" alt=".\img\absolute1.png"  />



<img src="/absolute2.png"  />

```html
p {
	color: white;
	background: #444444;
}
<body>
    <p>文本1文本1</p>
    <p style="position: absolute;">文本2文本2</p>
    <p>文本3文本3</p>
</body>
```

![image-20210314161727761](/image-20210314161727761.png)

absolute 的几个特性：

1. 设置 absolute 会使得inline元素被“块”化；
2. 设置absolute会使得元素已有的float失效。不过float和absolute同时使用的情况不多；
3. absolute会使元素悬浮在页面之上，如果有多个悬浮元素，则“后来者居上”
4. absolute元素脱离了文档结构。和relative不同，其他三个元素的位置重新排列了。只要元素会脱离文档结构，它就会产生破坏性，导致父元素坍塌。

原点位置不同

![image-20210313222027594](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210313222027594.png)

![image-20210313222136472](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210313222136472.png)

![image-20210313222244479](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210313222244479.png)

![image-20210313222404409](C:\Users\Administrator\AppData\Roaming\Typora\typora-user-images\image-20210313222404409.png)



## fixed

fixed永远根据浏览器确定位置。

# 伪元素

a:link {color:#FF0000;} /* 未访问的链接 */
a:visited {color:#00FF00;} / * 已访问的链接 */
a:hover {color:#FF00FF;} /* 鼠标划过链接 */
a:active {color:#0000FF;} /* 已选中的链接 */

> **注意：** 在CSS定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。
>
> **注意：** 在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。
>
> **注意：**伪类的名称不区分大小写。

# CSS属性选择器

CSS 属性选择器 ~=, |=, ^=, $=, *= 的区别

**"value 是完整单词"** 类型的比较符号: **~=**, **|=**

**"拼接字符串**" 类型的比较符号: ***=**, **^=**, **$=**

**1.attribute 属性中包含 value:**　

[attribute~=value] 属性中包含独立的单词为 value，例如：

```
[title~=flower]  -->  <img src="/i/eg_tulip.jpg" title="tulip flower" />
```

[attribute*=value] 属性中做字符串拆分，只要能拆出来 value 这个词就行，例如：

```
[title*=flower]   -->  <img src="/i/eg_tulip.jpg" title="ffffflowerrrrrr" />
```

**2.attribute 属性以 value 开头:**

[attribute|=value] 属性中必须是完整且唯一的单词，或者以 **-** 分隔开：，例如：

```
[lang|=en]     -->  <p lang="en">  <p lang="en-us">
```

attribute^=value] 属性的前几个字母是 value 就可以，例如：

```
[lang^=en]    -->  <p lang="ennn">
```

**3.attribute 属性以 value 结尾:**

```
[attribute$=value] 属性的后几个字母是 value 就可以，例如：
a[src$=".pdf"]
```

# 盒子模型

CSS3 `box-sizing` 属性可以设置 width 和 height 属性中包含了 padding(内边距) 和 border(边框)。

默认情况下，元素的宽度与高度计算方式如下：

**width(宽) + padding(内边距) + border(边框) = 元素实际宽度**

**height(高) + padding(内边距) + border(边框) = 元素实际高度**

如果在元素上设置了 `box-sizing: border-box;` 则 padding(内边距) 和 border(边框) 也包含在 width 和 height 中: