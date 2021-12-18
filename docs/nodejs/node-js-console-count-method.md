# Node.js console.count()方法

> 原文:[https://www.geeksforgeeks.org/node-js-console-count-method/](https://www.geeksforgeeks.org/node-js-console-count-method/)

**console.count()方法**是控制台模块的内置应用程序编程接口，用于通过维护特定标签的内部计数器，将传递给它的标签作为参数进行计数。

**语法:**

```js
console.count(label)
```

**参数:**该方法有一个参数如上所述，描述如下:

*   **Label:** is an optional parameter that specifies the label to be counted. The default value is Default Value.

**返回值:**此方法将使用指定标签调用的此函数的计数输出到 stdout。

下面的例子说明了在 Node.js 中使用 console.count()方法:

**例 1:**

```js
// Node.js program to demonstrate the   
// console.count() Method

// Accessing console module
const console = require('console');

// Calling console.count() 
console.count("a");
console.count("b");
console.count("a");
console.count("a");
console.count("a");
console.count("b");
console.count("b");
console.count("b");
```

**输出:**

```js
a: 1
b: 1
a: 2
a: 3
a: 4
b: 2
b: 3
b: 4

```

**例 2:**

```js
// Node.js program to demonstrate the   
// console.count() Method

// Accessing console module
const console = require('console');

// Calling console.count() method
// with no parameter to count
// default label
console.count();
console.count("a");
console.count("b");
console.count("a");
console.count("a");
console.count();
console.count();
console.count();
console.count("b");
```

**输出:**

```js
default: 1
a: 1
b: 1
a: 2
a: 3
default: 2
default: 3
default: 4
b: 2

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/console . html # console _ console _ count _ label](https://nodejs.org/api/console.html#console_console_count_label)