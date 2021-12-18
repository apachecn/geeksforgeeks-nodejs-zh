# Node.js util.types.isDate()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is date-method/](https://www.geeksforgeeks.org/node-js-util-types-isdate-method/)

**util.types.isDate()方法**是 util 模块的内置应用编程接口，用于检查节点. js 中日期的类型

**语法:**

```js
util.types.isDate( value )
```

**参数:**该方法接受如上所述和如下所述的单个参数。

*   **Value:** It is a required parameter of any data type.

**返回值:**返回一个布尔值，如果该值是日期对象，则为真，否则为假。

下面的例子说明了 util.types.isDate()方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// util.types.isDate() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter
// of util.types.isDate() method
var v1 = new Date();
var v2 = 3 / 6 / 96;

// Printing the returned value from
// util.types.isDate() method
console.log(util.types.isDate(v1));
console.log(util.types.isDate(v2));
```

**输出:**

```js
true
false

```

**例 2:**

```js
// Node.js program to demonstrate the   
// util.types.isDate() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter
// of util.types.isDate() method
var v1 = new Date();
var v2 = 3 / 6 / 96;

// Calling util.types.isDate() method
if (util.types.isDate(v1))
    console.log("The passed value is a Date.");
else
    console.log("The passed value is not a Date");

if (util.types.isDate(v2))
    console.log("The passed value is a Date.");
else
    console.log("The passed value is not a Date");
```

**输出:**

```js
The passed value is a Date.
The passed value is not a Date

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isdate _ value