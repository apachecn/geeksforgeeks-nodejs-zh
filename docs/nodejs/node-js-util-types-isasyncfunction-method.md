# node . js util . types . isasyncfunction()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isasyncfunction-method/](https://www.geeksforgeeks.org/node-js-util-types-isasyncfunction-method/)

**util.types.isAsyncFunction()方法**是 util 模块的一个内置应用编程接口，用于对 node.js.
中的异步函数进行类型检查**语法:**

```
util.types.isAsyncFunction( value )
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **值:**它是保存任何数据类型的必需参数。

**返回值:**它返回一个布尔值，如果从 JavaScript 引擎的角度来看，该值是异步函数，则为真，否则为假。
以下示例说明了在 Node.js 中使用 util.types.isAsyncFunction()方法:
**示例 1:**

## java 描述语言

```
// Node.js program to demonstrate the  
// util.types.isAsyncFunction() Method

// Allocating util module
const util = require('util');

// Functions to be passed as parameter of
// util.types.isAsyncFunction() method
var f2 = async function function2(){}
var f1 = function function1(){}

// Printing the returned value from
// util.types.isAsyncFunction() method
console.log(util.types.isAsyncFunction(f2));
console.log(util.types.isAsyncFunction(f1));
```

**输出:**

```
true
false
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the  
// util.types.isAsyncFunction() Method

// Allocating util module
const util = require('util');

// Functions to be passed as parameter
var f2 = async function function2() { }
var f1 = function function1() { }

// Calling util.types.isAsyncFunction() method
if (util.types.isAsyncFunction(f2))
    console.log("The passed value is an Async function.");
else
    console.log("The passed value is not an Async function");

if (util.types.isAsyncFunction(f1))
    console.log("The passed value is an Async function.");
else
    console.log("The passed value is not an Async function");
```

**输出:**

```
The passed value is an Async function.
The passed value is not an Async function
```

**注意:**以上程序将使用 node filename.js 命令编译运行。
**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isasyncfunction _ value](https://nodejs.org/api/util.html#util_util_types_isasyncfunction_value)