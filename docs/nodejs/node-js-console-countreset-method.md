# node . js console . countereset()方法

> 原文:[https://www . geesforgeks . org/node-js-console-countereset-method/](https://www.geeksforgeeks.org/node-js-console-countreset-method/)

**console . countereset()方法**是控制台模块的内置应用编程接口，用于重置作为参数传递给它的特定标签的计数。

**语法:**

```js
console.countReset( label );
```

**参数:**该方法有一个参数如上所述，描述如下:

*   **Label:** is an optional parameter, which is used to specify the label to reset the counter. The default value is Default Value.

**返回值:**此方法不提供任何输出，但为指定标签重置计数器。

以下示例说明了在 Node.js 中使用**console . countereset()方法**:

**例 1:**

```js
// Node.js program to demonstrate the 
// console.countReset() method

// Accessing console module
const console = require('console');

// Calling console.count() method 
console.count("a");
console.count("b");
console.count("a");
console.count("a");
console.count("a");
console.count("b");

// Resetting counter
console.countReset("a");
console.countReset("b");

console.count("a");
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
a: 1
b: 1

```

**例 2:**

```js
// Node.js program to demonstrate the 
// console.countReset() method

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

// Resetting counter
console.countReset();
console.countReset("a");
console.countReset("b");

console.count();
console.count("a");
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
default: 1
a: 1
b: 1

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/console . html # console _ console _ count reset _ label](https://nodejs.org/api/console.html#console_console_countreset_label)