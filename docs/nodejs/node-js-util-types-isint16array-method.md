# node . js util . types . isin 16 array()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isint 16 array-method/](https://www.geeksforgeeks.org/node-js-util-types-isint16array-method/)

**util.types.isInt16Array()方法**是 util 模块的内置应用编程接口，用于检查 node.js 中 Int16Array 的类型。

**语法:**

```js
util.types.isInt16Array( value )
```

**参数:**该方法接受如上所述和如下所述的单个参数。

*   **Value:** It is a required parameter to save any data type.

**返回值:**返回布尔值，如果值是 Int16Array 对象，则为真，否则为假。

下面的例子说明了在 Node.js 中 util.types.isInt16Array()方法的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// util.types.isInt16Array() Method 

// Allocating util module
const util = require('util');

// Value to be passed as parameter of
// util.types.isInt16Array() method
var v1 = new BigInt64Array();
var v2 = new BigUint64Array();
var v3 = new Float32Array();
var v4 = new Int8Array();
var v5 = new Int16Array();

// Printing the returned value from
// util.types.isInt16Array() method
console.log(util.types.isInt16Array(v1));
console.log(util.types.isInt16Array(v2));
console.log(util.types.isInt16Array(v3));
console.log(util.types.isInt16Array(v4));
console.log(util.types.isInt16Array(v5));
```

**输出:**

```js
false
false
false
false
true

```

**例 2:**

```js
// Node.js program to demonstrate the   
// util.types.isInt16Array() Method 

// Allocating util module
const util = require('util');

// Value to be passed as parameter of
// util.types.isInt16Array() method
var v1 = new Int8Array();
var v2 = new Int16Array();

// Calling util.types.isInt16Array() method
if (util.types.isInt16Array(v1))
    console.log("The passed value is a Int16Array.");
else
    console.log("The passed value is not a Int16Array");

if (util.types.isInt16Array(v2))
    console.log("The passed value is a Int16Array.");
else
    console.log("The passed value is not a Int16Array");
```

**输出:**

```js
The passed value is not a Int16Array.
The passed value is a Int16Array

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isint 16 array _ value