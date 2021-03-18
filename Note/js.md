# JavaScript 简介

JS直接写 HTML 输出流

> 如果您在文档加载后使用  document.write，会覆盖整个文档。

DOM (**D**ocument **O**bject **M**odel)（文档对象模型）是用于访问 HTML 元素的正式 W3C 标准。

HTML 中的脚本必须位于 `<script>` 与 `</script>` 标签之间。

JavaScript 可以通过不同的方式来输出数据：

- 使用 **window.alert()** 弹出警告框。
- 使用 **document.write()** 方法将内容写到 HTML 文档中。
- 使用 **innerHTML** 写入到 HTML 元素。
- 使用 **console.log()** 写入到浏览器的控制台。

# JavaScript 语法

## 变量

- 局部变量：在函数中通过var声明的变量。

- 全局变量：在函数外通过var声明的变量。

- 没有声明就使用的变量，默认为全局变量，不论这个变量在哪被使用。

```javascript
function func(){
  undefined_var=110
}
```

在 func() 被第一次调用之前， undefined_var 变量是不存在的即 undefined。func() 被调用过之后，undefined_var 成为全局变量。

### ES6 中的 let 关键字

let 允许你声明一个作用域被限制在块级中的变量、语句或者表达式。与var关键字不同的是，它声明的变量只能是全局或者整个函数块的。

for 循环很适合使用 let

```javascript
for (let i = 0; i < 10; i++) {
  // ...
}
// 计数器i只在for循环体内有效，在循环体外引用就会报错。
```

### 变量提升（hoisting）

JavaScript 中，函数及变量的声明都将被提升到函数的最顶部。变量可以在使用后声明。

JavaScript 只有声明的变量会提升，初始化的不会。

## 数据类型

### 值类型(基本类型)

字符串（String）

数字(Number)

布尔(Boolean)

对空（Null）：只有一个值的特殊类型。表示一个空对象引用。可用来清空对象

未定义（Undefined）：**undefined** 是一个没有设置值的变量。

Symbol

### 引用数据类型

对象(Object)、数组(Array)、函数(Function)。

> **注：**Symbol 是 ES6 引入了一种新的原始数据类型，表示独一无二的值。

### undefined 和 null

- undefined：是所有没有赋值变量的默认值，自动赋值。
- null：主动释放一个变量引用的对象，表示一个变量不再指向任何对象地址。

**何时使用null?**

当使用完一个比较大的对象时，需要对其进行释放内存时，设置为 null。

**3、null 与 undefined 的异同点是什么呢？**

**共同点**：都是原始类型，保存在栈中变量本地。

**不同点**：

（1）undefined：表示**变量声明过但并未赋过值**。

（2）null：变量初始化了，但是什么值都没给，只给了一个空对象。一般用于**主动释放指向对象的引用**，例如：

```javascript
var emps = ['ss','nn'];
emps = null;     // 释放指向数组的引用
```

null 和 undefined 的值相等，但类型不等：

```javascript
typeof undefined             // undefined
typeof null                  // object
null === undefined           // false
null == undefined            // true
```



### 数组 Array

- 数组也是对象
- 和普通对象不同的是数组使用索引操作属性
- 数组的存储性能比普通对象好，所以开发中常用数组。
- 读取不存在的索引，返回 undefined
- 数组元素可以是任意数据类型

`var arr = ["hello",  1, true, undefined, {name: "Jacket"}, {age: 18}];`

```javascript
var arr = new QArray();
console.log(typeof arr);	// Object

console.log(arr.length);	// 查询数组长度
arr.length = 3;			// 设置数组长度

/* 添加数据的好方法 */
arr[arr.length] = 10;	// 向数组尾添加元素
```

数组的三种写法：

```javascript
new Array();
new Array(size);
new Array(element0, element1, ..., elementn);
var arr = [element0, element1, ..., elementn];
```

## Array 对象方法

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [concat()](https://www.w3school.com.cn/jsref/jsref_concat_array.asp) | 连接两个或更多的数组，并返回结果。                           |
| [join()](https://www.w3school.com.cn/jsref/jsref_join.asp)   | 把数组的所有元素放入一个字符串。元素通过指定的分隔符进行分隔。 |
| [pop()](https://www.w3school.com.cn/jsref/jsref_pop.asp)     | 删除并返回数组的最后一个元素                                 |
| [push()](https://www.w3school.com.cn/jsref/jsref_push.asp)   | 向数组的末尾添加一个或更多元素，并返回新的长度。             |
| [reverse()](https://www.w3school.com.cn/jsref/jsref_reverse.asp) | 颠倒数组中元素的顺序。                                       |
| [shift()](https://www.w3school.com.cn/jsref/jsref_shift.asp) | 删除并返回数组的第一个元素                                   |
| [slice()](https://www.w3school.com.cn/jsref/jsref_slice_array.asp) | 从某个已有的数组返回选定的元素。                             |
| [sort()](https://www.w3school.com.cn/jsref/jsref_sort.asp)   | 对数组的元素进行排序                                         |
| [splice()](https://www.w3school.com.cn/jsref/jsref_splice.asp) | 删除元素，并向数组添加新元素。                               |
| [toSource()](https://www.w3school.com.cn/jsref/jsref_tosource_array.asp) | 返回该对象的源代码。                                         |
| [toString()](https://www.w3school.com.cn/jsref/jsref_toString_array.asp) | 把数组转换为字符串，并返回结果。                             |
| [toLocaleString()](https://www.w3school.com.cn/jsref/jsref_toLocaleString_array.asp) | 把数组转换为本地数组，并返回结果。                           |
| [unshift()](https://www.w3school.com.cn/jsref/jsref_unshift.asp) | 向数组的开头添加一个或更多元素，并返回新的长度。             |
| [valueOf()](https://www.w3school.com.cn/jsref/jsref_valueof_array.asp) | 返回数组对象的原始值                                         |

forEach

```javascript
array.forEach(function(currentValue, index, arr), thisValue)
```

| 参数                                 | 描述                                                         |
| :----------------------------------- | :----------------------------------------------------------- |
| *function*(currentValue, index, arr) | currentValue*必需。当前元素;  index。当前元素的索引值。*arr可选。当前元素所属的数组对象。 |
| *thisValue*                          | 可选。传递给函数的值一般用 "this" 值。 如果这个参数为空， "undefined" 会传递给 "this" 值 |

### 对象

JavaScript 对象是键值对的容器，“键”必须为字符串，“值” 可以是 JavaScript 中包括 null 和 undefined 的任意数据类型。

JavaScript对象:属性和方法的容器;

对象的属性之间一定要用逗号隔开;

对象的方法定义了一个函数，并作为对象的属性存储。

对象方法通过添加 **()** 调用 (作为一个函数)。

## 函数

```javascript
function functionname() {
    // 执行代码
}
```



```javascript
function myFunction(var1,var2) {
	//代码
}
```

向未声明的 JavaScript 变量分配值，变量将被自动作为 window 的一个属性。

非严格模式下给未声明变量赋值创建的全局变量，是全局对象的可配置属性，可以删除。

```javascript
var var1 = 1; // 不可配置全局属性
var2 = 2; // 没有使用 var 声明，可配置全局属性

console.log(this.var1); // 1
console.log(window.var1); // 1
console.log(window.var2); // 2

delete var1; // false 无法删除
console.log(var1); //1

delete var2; 
console.log(delete var2); // true
console.log(var2); // 已经删除 报错变量未定义
```





## 数据类型转换

**Number()** 转换为数字， **String()** 转换为字符串， **Boolean()** 转换为布尔值。

在 JavaScript 中有 6 种不同的数据类型：

- string
- number
- boolean
- object
- function
- symbol

3 种对象类型：

- Object
- Date
- Array

2 个不包含任何值的数据类型：

- null
- undefined

**constructor** 属性返回所有 JavaScript 变量的构造函数。

```javascript
"John".constructor                 // 返回函数 String()  { [native code] }
(3.14).constructor                 // 返回函数 Number()  { [native code] }
false.constructor                  // 返回函数 Boolean() { [native code] }
[1,2,3,4].constructor              // 返回函数 Array()   { [native code] }
{name:'John', age:34}.constructor  // 返回函数 Object()  { [native code] }
new Date().constructor             // 返回函数 Date()    { [native code] }
function () {}.constructor         // 返回函数 Function(){ [native code] }
```



利用 constructor 属性判断对象类型是否为数组

```javascript
function isArray(myArray) {
    return myArray.constructor.toString().indexOf("Array") > -1;
}
```

利用 constructor 属性判断对象类型是否为日期

```javascript
function isDate(myDate) {
    return myDate.constructor.toString().indexOf("Date") > -1;
}
```



| 方法            | 描述                                                 |
| --------------- | ---------------------------------------------------- |
| toExponential() | 把对象的值转换为指数计数法。                         |
| toFixed()       | 把数字转换为字符串，结果的小数点后有指定位数的数字。 |
| toPrecision()   | 把数字格式化为指定的长度。                           |
| String()        | 数字转字符串。                                       |
| toString()      | 字符串转数字。                                       |
| Number()        | 字符串转数字。                                       |
| parseFloat()    | 解析一个字符串，并返回一个浮点数。                   |
| parseInt()      | 解析一个字符串，并返回一个整数。                     |
|                 |                                                      |

将 bool 转换为数字

```javascript
Number(false)     // 返回 0
Number(true)      // 返回 1
```

bool 转换为字符串

```javascript
String(false)        // 返回 "false"
String(true)         // 返回 "true"
false.toString()     // 返回 "false"
true.toString()      // 返回 "true"
```

日期的转换

```javascript
d = new Date();
Number(d);		// 返回 1404568027739, 1970 年 1 月 1 日至今的毫秒数。

Date();
String(new Date());	// Mon Mar 15 2021 15:16:05 GMT+0800 (中国标准时间)

obj = new Date()
obj.toString() 
```



typeof 检测一个变量是否存在

```javascript
if(typeof a!="undefined") {}
```

因为 typeof 遇到 null,数组,对象时都会返回 object 类型，所以判断一个对象是否是数组或者判断某个变量是否是某个对象的实例则要选择使用另一个关键语法 **instanceof**

语法格式：`var result = objectName instanceof objectType`

返回值：如果是指定类型返回 true，否则返回 false：



## 事件

常用的 HTML事件

| 事件        | 描述                         |
| ----------- | ---------------------------- |
| onchange    | HTML 元素改变                |
| onclick     | 用户点击 HTML 元素           |
| onmouseover | 用户在一个HTML元素上移动鼠标 |
| onmouseout  | 用户从一个HTML元素上移开鼠标 |
| onkeydown   | 用户按下键盘按键             |
| onload      | 浏览器已完成页面的加载       |

因为遵从**“高内聚，低耦合”**的编程原则，不推荐使用 HTML 元素中可以添加事件属性 的方式来添加属性。

```javascript
<button onclick="getElementById('demo').innerHTML=Date()">现在的时间是?</button>
```

## 字符串

不要创建 String 对象。它会拖慢执行速度，并可能产生其他副作用：

=== 为绝对相等，即数据类型与值都必须相等。

| 方法                | 描述                                                         |
| ------------------- | ------------------------------------------------------------ |
| charAt()            | 返回指定索引位置的字符                                       |
| charCodeAt()        | 返回指定索引位置字符的 Unicode 值                            |
| concat()            | 连接两个或多个字符串，返回连接后的字符串                     |
| fromCharCode()      | 将 Unicode 转换为字符串                                      |
| indexOf()           | 返回字符串中检索指定字符第一次出现的位置                     |
| lastIndexOf()       | 返回字符串中检索指定字符最后一次出现的位置                   |
| localeCompare()     | 用本地特定的顺序来比较两个字符串                             |
| match()             | 找到一个或多个正则表达式的匹配                               |
| replace()           | 替换与正则表达式匹配的子串                                   |
| search()            | 检索与正则表达式相匹配的值                                   |
| slice()             | 提取字符串的片断，并在新的字符串中返回被提取的部分           |
| split()             | 把字符串分割为子字符串数组                                   |
| substr()            | 从起始索引号提取字符串中指定数目的字符                       |
| substring()         | 提取字符串中两个指定的索引号之间的字符                       |
| toLocaleLowerCase() | 根据主机的语言环境把字符串转换为小写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLocaleUpperCase() | 根据主机的语言环境把字符串转换为大写，只有几种语言（如土耳其语）具有地方特有的大小写映射 |
| toLowerCase()       | 把字符串转换为小写                                           |
| toString()          | 返回字符串对象值                                             |
| toUpperCase()       | 把字符串转换为大写                                           |
| trim()              | 移除字符串首尾空白                                           |
| valueOf()           | 返回某个字符串对象的原始值                                   |

### JavaScript == 与 === 区别

1、对于 string、number 等基础类型，== 和 === 是有区别的

- a）不同类型间比较，== 之比较 "转化成同一类型后的值" 看 "值" 是否相等，=== 如果类型不同，其结果就是不等。
-  b）同类型比较，直接进行 "值" 比较，两者结果一样。

2、对于 Array,Object 等高级类型，== 和 === 是没有区别的

进行 "指针地址" 比较

3、基础类型与高级类型，== 和 === 是有区别的

- a）对于 ==，将高级转化为基础类型，进行 "值" 比较
-  b）因为类型不同，=== 结果为 false

### 逻辑与 &&

如果运算的第一个操作数为true,则返回第二个操作数,反之则返回第一个操作数。

### 逻辑或 ||

如果运算的第一个操作数为 true,则返回第一个操作数,反之则返回第二个操作数。

- **for** : 比较适合遍历数组,字符串等等。
-  **for in** : 比较适合遍历对象，遍历对象时使用这个再合适不过了。
-  **while** : while 的话，与 for 的使用场景差不多。唯一不同的是，遍历的条件必须满足。
-  **do while** : 至少执行一边的循环，遍历数组和字符串也是很方便。

## Date

日期变为字符串的函数

| 方法              | 描述                                        |
| ----------------- | ------------------------------------------- |
| getDate()         | 从 Date 对象返回一个月中的某一天 (1 ~ 31)。 |
| getDay()          | 从 Date 对象返回一周中的某一天 (0 ~ 6)。    |
| getFullYear()     | 从 Date 对象以四位数字返回年份。            |
| getHours()        | 返回 Date 对象的小时 (0 ~ 23)。             |
| getMilliseconds() | 返回 Date 对象的毫秒(0 ~ 999)。             |
| getMinutes()      | 返回 Date 对象的分钟 (0 ~ 59)。             |
| getMonth()        | 从 Date 对象返回月份 (0 ~ 11)。             |
| getSeconds()      | 返回 Date 对象的秒数 (0 ~ 59)。             |
| getTime()         | 返回 1970 年 1 月 1 日至今的毫秒数。        |

## 正则表达式

### 简介

**search() ** 用于检索字符串中指定的子字符串，或检索与正则表达式相匹配的子字符串，并返回子串的起始位置。

**replace() ** 用于在字符串中用一些字符替换另一些字符，或替换一个与正则表达式匹配的子串。

`var patt = /runoob/i`

- **/runoob/i**  是一个正则表达式。
- **runoob**  是一个**正则表达式主体** (用于检索)。
- **i**  是一个**修饰符** (搜索不区分大小写)。

**修饰符** 可以在全局搜索中不区分大小写:

| 修饰符 | 描述                                                     |
| ------ | -------------------------------------------------------- |
| i      | 执行对大小写不敏感的匹配。                               |
| g      | 执行全局匹配（查找所有匹配而非在找到第一个匹配后停止）。 |
| m      | 执行多行匹配。                                           |

### 正则表达式方法

test() 方法用于检测一个字符串是否匹配某个模式，如果字符串中含有匹配的文本，则返回 true，否则返回 false。

## 调试

1. console.log(x);
2. 设置断点
3. debugger 关键字

**debugger** 关键字用于停止执行 JavaScript，并调用调试函数。这个关键字与在调试工具中设置断点的效果是一样的。



## 严格模式

"use strict" 指令在 JavaScript 1.8.5 (ECMAScript5) 中新增。它不是一条语句，但是是一个字面量表达式，在 JavaScript 旧版本中会被忽略。

"use strict" 的目的是指定代码在严格条件下执行。

> 支持严格模式的浏览器: Internet Explorer 10 +、 Firefox 4+ Chrome 13+、 Safari 5.1+、 Opera 12+。

为什么使用严格模式:

- 消除代码运行的一些不安全之处，保证代码运行的安全；
- 提高编译器效率，增加运行速度；
- 为未来新版本的Javascript做好铺垫。

> "use strict" 指令只允许出现在脚本或函数的开头。

### 严格模式的限制

不允许使用未声明的变量：

不允许删除变量或对象。

不允许删除函数。

不允许变量重名

不允许使用八进制 

不允许使用转义字符

不允许对只读属性赋值

不允许对一个使用getter方法读取的属性进行赋值

不允许删除一个不允许删除的属性

变量名不能使用 "arguments" 字符串:

不允许使用以下这种语句

```javascript
"use strict";
with (Math){x = cos(2)}; // 报错
```

由于一些安全原因，在作用域 eval() 创建的变量不能被调用

禁止this关键字指向全局对象

```javascript
function f(){
    return !this;
} 
// 返回false，因为"this"指向全局对象，"!this"就是false

function f(){ 
    "use strict";
    return !this;
} 
// 返回true，因为严格模式下，this的值为undefined，所以"!this"为true。
```

### 比较运算符

在常规的比较中，数据类型是被忽略的，以下 if 条件语句返回 true：

```javascript
var x = 10;
var y = "10";
if (x == y)
```

在严格的比较运算中，=== 为恒等计算符，同时检查表达式的值与类型，以下 if 条件语句返回 false：

```javascript
var x = 10;
var y = "10";
if (x === y)
```

这种错误经常会在 switch 语句中出现，switch 语句会使用恒等计算符 (===) 进行比较。



## this指针

**this 的多种指向:**

-  1、在对象方法中， this 指向调用它所在方法的对象。
-  2、单独使用 this，它指向全局(Global)对象。
-  3、函数使用中，this 指向函数的所属者。
-  4、严格模式下函数是没有绑定到 this 上，这时候 this 是 undefined。
-  5、在 HTML 事件句柄中，this 指向了接收事件的 HTML 元素。
-  6、apply 和 call 允许切换函数执行的上下文环境（context），即 this 绑定的对象，可以将 this 引用到任何对象。