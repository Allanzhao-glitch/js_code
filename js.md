# 一、JavaScript 用法

HTML 中的 Javascript 脚本代码必须位于 <script> 与 </script> 标签之间。

Javascript 脚本代码可被放置在 HTML 页面的 <body> 和 <head> 部分中。

1、<script> 标签

如需在 HTML 页面中插入 JavaScript，请使用 <script> 标签。

<script> 和 </script> 会告诉 JavaScript 在何处开始和结束。

<script> 和 </script> 之间的代码行包含了 JavaScript:

<body> 中的 JavaScript

在本例中，JavaScript 会在页面加载时向 HTML 的 <body> 写文本：

```javascript
<!DOCTYPE html>
<html>
<body>
.
.
<script>
document.write("<h1>这是一个标题</h1>");
document.write("<p>这是一个段落</p>");
</script>
.
.
</body>
</html>
```

JavaScript 函数和事件

通常，我们需要在某个事件发生时执行代码，比如当用户点击按钮时。如果我们把 JavaScript 代码放入函数中，就可以在事件发生时调用该函数。

2、在 <head> 或者 <body> 的JavaScript

可以在 HTML 文档中放入不限数量的脚本。

脚本可位于 HTML 的 <body> 或 <head> 部分中，或者同时存在于两个部分中。

通常的做法是把函数放入 <head> 部分中，或者放在页面底部。这样就可以把它们安置到同一处位置，不会干扰页面的内容。

①、<head> 中的 JavaScript 函数

把一个 JavaScript 函数放置到 HTML 页面的 <head> 部分。

该函数会在点击按钮时被调用：

```javascript
<!DOCTYPE html>
<html>
<head>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</head>
<body>
<h1>我的 Web 页面</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">尝试一下</button>
</body>
</html>
```

②、<body> 中的 JavaScript 函数

把一个 JavaScript 函数放置到 HTML 页面的 <body> 部分。

该函数会在点击按钮时被调用：

```javascript
<!DOCTYPE html>
<html>
<body>
<h1>我的 Web 页面</h1>
<p id="demo">一个段落</p>
<button type="button" onclick="myFunction()">尝试一下</button>
<script>
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
</script>
</body>
</html>
```

③、外部的 JavaScript

可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。

外部 JavaScript 文件的文件扩展名是 .js。

如需使用外部文件，请在 <script> 标签的 "src" 属性中设置该 .js 文件：

```javascript
<!DOCTYPE html>
<html>
<body>
<script src="myScript.js"></script>
</body>
</html>
```

可以将脚本放置于 <head> 或者 <body>中，放在 <script> 标签中的脚本与外部引用的脚本运行效果完全一致。

myScript.js 文件代码如下：

```javascript
function myFunction()
{
    document.getElementById("demo").innerHTML="我的第一个 JavaScript 函数";
}
```

![](C:\Users\Allan\AppData\Roaming\marktext\images\2025-11-13-16-06-02-image.png)

node test.js

# 二、 JavaScript 输出

JavaScript 没有任何打印或者输出的函数。

JavaScript 显示数据

JavaScript 可以通过不同的方式来输出数据：

- 使用 **window.alert()** 弹出警告框。
- 使用 **document.write()** 方法将内容写到 HTML 文档中。
- 使用 **innerHTML** 写入到 HTML 元素。
- 使用 **console.log()** 写入到浏览器的控制台。

## 1、使用 window.alert()

可以弹出警告框来显示数据：

```javascript
<!DOCTYPE html>
<html>
<body>
<h1>我的第一个页面</h1><p>我的第一个段落。</p>
	
<script>window.alert(5 + 6);
</script>

</body>
</html>
```

## 2、操作 HTML 元素

如需从 JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(*id*) 方法。

请使用 "id" 属性来标识 HTML 元素，并 innerHTML 来获取或插入元素内容：

```javascript
<!DOCTYPE html><html>
<body>

<h1>我的第一个 Web 页面</h1>

	<p id="demo">我的第一个段落</p>

<script>
	document.getElementById("demo").innerHTML = "段落已修改。";
</script>

</body>
</html>
```

以上 JavaScript 语句（在 <script> 标签中）可以在 web 浏览器中执行：

**document.getElementById("demo")** 是使用 id 属性来查找 HTML 元素的 JavaScript 代码 。

**innerHTML = "段落已修改。"** 是用于修改元素的 HTML 内容(innerHTML)的 JavaScript 代码。

## 3、写到 HTML 文档

```javascript
<!DOCTYPE html><html>
<body><h1>我的第一个 Web 页面</h1>
	<p>我的第一个段落。</p>
	<script>document.write(Date());
</script>

</body>
</html>
```

使用 document.write() 可以向文档写入内容。

如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖。

## 4、写到控制台

如果您的浏览器支持调试，你可以使用 **console.log()** 方法在浏览器中显示 JavaScript 值。

浏览器中使用 F12 来启用调试模式， 在调试窗口中点击 "Console" 菜单。

```javascript
<!DOCTYPE html>
<html>
<body>
<h1>我的第一个 Web 页面</h1>
<script>
a = 5;
b = 6;
c = a + b;
console.log(c);
</script>

</body>
</html>
```

# 三、JavaScript变量

变量是用于存储信息的"容器"。

在 JavaScript 中，变量用于存储数据，并可以在程序执行过程中动态更改。

在 JavaScript 中，变量可以存储各种类型的数据，如数字、字符串、对象、函数等。

变量名是标识符，用于引用存储在变量中的数据。

在 JavaScript 中，可以使用 var、let 和 const 关键字来声明变量。

- **`var`**：ES5 引入的变量声明方式，具有函数作用域。

- **`let`**：ES6 引入的变量声明方式，具有块级作用域。

- **`const`**：ES6 引入的常量声明方式，具有块级作用域，且值不可变。

与代数一样，JavaScript 变量可用于存放值（比如 x = 5）和表达式（比如 z = x + y）。

变量可以使用短名称（比如 x 和 y），也可以使用描述性更好的名称（比如 age, sum, totalvolume）。

- 变量必须以字母开头
- 变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）
- 变量名称对大小写敏感（y 和 Y 是不同的变量）

## 1、JavaScript 数据类型

JavaScript 变量还能保存其他数据类型，比如文本值 (name="Bill Gates")。

在 JavaScript 中，类似 "Bill Gates" 这样一条文本被称为字符串。

JavaScript 变量有很多种类型，但是现在，我们只关注数字和字符串。

当您向变量分配文本值时，应该用双引号或单引号包围这个值。

当您向变量赋的值是数值时，不要使用引号。如果您用引号包围数值，该值会被作为文本来处理。

## 2、 声明（创建） JavaScript 变量

在 JavaScript 中创建变量通常称为"声明"变量。

我们使用 var 关键词来声明变量：

变量声明之后，该变量是空的（它没有值）。

如需向变量赋值，请使用等号：

不过，您也可以在声明变量时对其赋值：

在下面的例子中，我们创建了名为 carname 的变量，并向其赋值 "Volvo"，然后把它放入 id="demo" 的 HTML 段落中：

```javascript
var carname="Volvo";
document.getElementById("demo").innerHTML=carname;
```

**var 声明特点：**

- 变量可以重复声明（覆盖原变量）。
- 变量未赋值时，默认值为 undefined。
- var 声明的变量会提升（Hoisting），但不会初始化

一条语句，多个变量

可以在一条语句中声明很多变量。该语句以 var 开头，并使用逗号分隔变量即可：

重新声明 JavaScript 变量

如果重新声明 JavaScript 变量，该变量的值不会丢失：

在以下两条语句执行后，变量 carname 的值依然是 "Volvo"：

```javascript
var
carname="Volvo"; 
var carname;
```

使用 const 关键字来定义一个常量，即一旦赋值后，变量的值不能再被修改。，使用 let 关键字定义的限定范围内作用域的变量

# 四、JavaScript 数据类型

**值类型(基本类型)**：字符串（String）、数字(Number)、布尔(Boolean)、空（Null）、未定义（Undefined）、Symbol。

**引用数据类型（对象类型）**：对象(Object)、数组(Array)、函数(Function)，还有两个特殊的对象：正则（RegExp）和日期（Date）。

JavaScript 拥有动态类型

JavaScript 拥有动态类型。这意味着相同的变量可用作不同的类型：

变量的数据类型可以使用 typeof 操作符来查看

**typeof [1,2,3,4] 返回 "object"**，这是 JavaScript 早期设计的一个"缺陷"，数组本质上是特殊类型的对象。

正确检测数组的方法：

```javascript
Array.isArray([1,2,3]); // true
[1,2,3] instanceof Array; // true
```

JavaScript 字符串

字符串是存储字符（比如 "Bill Gates"）的变量。

字符串可以是引号中的任意文本。您可以使用单引号或双引号：

声明变量类型

当您声明新变量时，可以使用关键词 "new" 来声明其类型：

```javascript
var carname=new String;
var x=      new Number;
var y=      new Boolean;
var cars=   new Array;
var person= new Object;
```

# 五、 JavaScript 对象

JavaScript 对象是拥有属性和方法的数据。

## 1、对象属性

可以说 "JavaScript 对象是变量的容器"。

但是，我们通常认为 "JavaScript 对象是键值对的容器"。

键值对通常写法为 **name : value** (键与值以冒号分割)。

键值对在 JavaScript 对象通常称为 **对象属性**。

## 2、访问对象属性

可以通过两种方式访问对象属性:

```javascript
person.lastName;
person["lastName"];
```

## 3、对象方法

对象的方法定义了一个函数，并作为对象的属性存储。

对象方法通过添加 () 调用 (作为一个函数)。

该实例访问了 person 对象的 fullName() 方法:

```javascript
name = person.fullName();
```

如果你要访问 person 对象的 fullName 属性，它将作为一个定义函数的字符串返回：

## 4、 访问对象方法

可以使用以下语法创建对象方法：

```javascript
methodName : function() {
    // 代码 
}
```

可以使用以下语法访问对象方法：

```js
objectName.methodName()
```

通常 fullName() 是作为 person 对象的一个方法， fullName 是作为一个属性。

如果使用 fullName 属性，不添加 **()**, 它会返回函数的定义：

# 六、 JavaScript 函数
