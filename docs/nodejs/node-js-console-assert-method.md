# Node.js console.assert()方法

> 原文:[https://www . geesforgeks . org/node-js-console-assert-method/](https://www.geeksforgeeks.org/node-js-console-assert-method/)

**console.assert()方法**是控制台模块的一个内置应用编程接口，用于断言作为参数传递给它的值，即检查该值是否为真，如果提供了错误消息并且未能断言该值，则打印错误消息。

**语法:**

```
console.assert(value, messages)
```

**参数:**该方法有两个参数，如上所述，描述如下:

*   **值:**此参数指定要声明的值。
*   **消息:**指定用作错误消息的消息。任何随值传递的参数都将被视为消息。

**返回值:**如果值为真，这个方法不返回任何东西。如果未能断言该值，则**断言失败**将被记录，随后会出现一条错误消息(如果在 util.format()中的值之后的所有后续参数中提供的话)。输出用作错误消息。

下面的例子说明了 console.assert()方法在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// console.assert() Method

// Accessing console module
const console = require('console');

// Calling console.assert() method
console.assert(true, "error message 1");
console.assert(false, "error message 2");
```

**输出:**

```
Assertion failed: error message 2
```

**例 2:**

```
// Node.js program to demonstrate the   
// console.assert() Method

// Accessing console module
const console = require('console');

// Calling console.assert()
var a = 10, b = 5;

console.assert(1 == 1, "error at 1==1");
console.assert(1 != 1, "error at 1==1");
console.assert(3 & 9, "error at 3&9");
console.assert(1 & 6, "error at 1&6");
console.assert(0 && 9, "error at 0&&9");
console.assert(1 && 8, "error at 1&&9");
console.assert(a % b == 1, "error at a%b==1");
console.assert(a > b, "error at a>b");
console.assert(b > a, "error at b>a");
```

**输出:**

```
Assertion failed: error at 1==1
Assertion failed: error at 1&6
Assertion failed: error at 0&&9
Assertion failed: error at a%b==1
Assertion failed: error at b>a

```

**注意:**以上程序使用`node filename.js`命令编译运行。
**参考:**[https://nodejs . org/API/console . html # console _ console _ assert _ value _ message](https://nodejs.org/api/console.html#console_console_assert_value_message)