# XML 教程

XML 指可扩展标记语言（e**X**tensible **M**arkup **L**anguage）。

XML 被设计用来传输和存储数据。

XML 很重要，也很容易学习。

## 什么是 XML？

- XML 指可扩展标记语言（EXtensible Markup Language）。
- XML 是一种很像HTML的标记语言。
- XML 的设计宗旨是传输数据，而不是显示数据。
- XML 标签没有被预定义。您需要自行定义标签。
- XML 被设计为具有自我描述性。
- XML 是 W3C 的推荐标准。

## XML 和 HTML 之间的差异

XML 不是 HTML 的替代。

XML 和 HTML 为不同的目的而设计：

- XML 被设计用来传输和存储数据，其焦点是数据的内容。
- HTML 被设计用来显示数据，其焦点是数据的外观。

HTML 旨在显示信息，而 XML 旨在传输信息。

## 通过 XML 您可以发明自己的标签

上面实例中的标签没有在任何 XML 标准中定义过（比如 <to> 和 <from>）。这些标签是由 XML 文档的创作者发明的。

这是因为 XML 语言没有预定义的标签。

HTML 中使用的标签都是预定义的。HTML 文档只能使用在 HTML 标准中定义过的标签（如 <p>、<h1> 等等）。

XML 允许创作者定义自己的标签和自己的文档结构。

## XML 不是对 HTML 的替代

**XML 是对 HTML 的补充。**

XML 不会替代 HTML，理解这一点很重要。在大多数 Web 应用程序中，XML 用于传输数据，而 HTML 用于格式化并显示数据。

对 XML 最好的描述是：

**XML 是独立于软件和硬件的信息传输工具。**





### xml声明

```xml
<?xml version="1.0" encoding="utf-8"?>
```

## 所有的 XML 元素都必须有一个关闭标签

## 实体引用

在 XML 中，一些字符拥有特殊的意义。

如果您把字符 "<" 放在 XML 元素中，会发生错误，这是因为解析器会把它当作新元素的开始。

这样会产生 XML 错误：

```xml
<message>if salary < 1000 then</message>
```

为了避免这个错误，请用**实体引用**来代替 "<" 字符：

```xml
<message>if salary &lt; 1000 then</message>
```

在 XML 中，有 5 个预定义的实体引用：

| \&lt;   | <    | less than      |
| ------- | ---- | -------------- |
| \&gt;   | >    | greater than   |
| \&amp;  | &    | ampersand      |
| \&apos; | '    | apostrophe     |
| \&quot; | "    | quotation mark |

> **注释：**在 XML 中，只有字符 "<" 和 "&" 确实是非法的。大于号是合法的，但是用实体引用来代替它是一个好习惯。

## XML 中的注释

在 XML 中编写注释的语法与 HTML 的语法很相似。

```
<!-- This is a comment -->
```

## 在 XML 中，空格会被保留

## XML 以 LF 存储换行

在 Windows 应用程序中，换行通常以一对字符来存储：回车符（CR）和换行符（LF）。

在 Unix 和 Mac OSX 中，使用 LF 来存储新行。

在旧的 Mac 系统中，使用 CR 来存储新行。

XML 以 LF 存储换行。

## 什么是 XML 元素？

XML 元素指的是从（且包括）开始标签直到（且包括）结束标签的部分。

一个元素可以包含：

- 其他元素
- 文本
- 属性
- 或混合以上所有...

## XML 命名规则

XML 元素必须遵循以下命名规则：

- 名称可以包含字母、数字以及其他的字符
- 名称不能以数字或者标点符号开始
- 名称不能以字母 xml（或者 XML、Xml 等等）开始
- 名称不能包含空格

> 可使用任何名称，没有保留的字词。

## XML 属性

在 HTML 中，属性提供有关元素的额外信息：

```xml
<img src="computer.gif">
<a href="demo.html">
```

属性通常提供不属于数据组成部分的信息。在下面的实例中，文件类型与数据无关，但是对需要处理这个元素的软件来说却很重要：

```xml
<file type="gif">computer.gif</file>
```



## XML 属性必须加引号

属性值必须被引号包围，不过单引号和双引号均可使用。比如一个人的性别，person 元素可以这样写：

\<person sex="female">

或者这样也可以：

```XML
<person sex='female'>
```

如果属性值本身包含双引号，您可以使用单引号，就像这个实例：

```XML
<gangster name='George "Shotgun" Ziegler'>
```

或者您可以使用字符实体：

```XML
<gangster name="George &quot;Shotgun&quot; Ziegler">
```

## XML 元素 和 属性的选择

```xml
<person sex="female">
<firstname>Anna</firstname>
<lastname>Smith</lastname>
</person>

<person>
<sex>female</sex>
<firstname>Anna</firstname>
<lastname>Smith</lastname>
</person>
```

在第一个实例中，sex 是一个属性。在第二个实例中，sex 是一个元素。这两个实例都提供相同的信息。

没有什么规矩可以告诉我们什么时候该使用属性，而什么时候该使用元素。我的经验是在 HTML 中，属性用起来很便利，但是在 XML 中，您应该尽量避免使用属性。如果信息感觉起来很像数据，那么请使用元素吧。

## 避免 XML 属性？

因使用属性而引起的一些问题：

- 属性不能包含多个值（元素可以）
- 属性不能包含树结构（元素可以）
- 属性不容易扩展（为未来的变化）

属性难以阅读和维护。请尽量使用元素来描述数据。而仅仅使用属性来提供与数据无关的信息。

不要做这样的蠢事（这不是 XML 应该被使用的方式）：

```xml
<note day="10" month="01" year="2008"
to="Tove" from="Jani" heading="Reminder"
body="Don't forget me this weekend!">
</note>
```

## 针对元数据的 XML 属性

有时候会向元素分配 ID 引用。这些 ID 索引可用于标识 XML 元素，它起作用的方式与 HTML 中 id 属性是一样的。这个实例向我们演示了这种情况：

```xml
<messages>
<note id="501">
<to>Tove</to>
<from>Jani</from>
<heading>Reminder</heading>
<body>Don't forget me this weekend!</body>
</note>
<note id="502">
<to>Jani</to>
<from>Tove</from>
<heading>Re: Reminder</heading>
<body>I will not</body>
</note>
</messages>
```

上面的 id 属性仅仅是一个标识符，用于标识不同的便签。它并不是便签数据的组成部分。

在此我们极力向您传递的理念是：元数据（有关数据的数据）应当存储为属性，而数据本身应当存储为元素。