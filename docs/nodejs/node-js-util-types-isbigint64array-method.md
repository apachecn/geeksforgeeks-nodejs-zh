# node . js | util . types . is initit 64 array()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is initit 64 array-method/](https://www.geeksforgeeks.org/node-js-util-types-isbigint64array-method/)

**util.types.isBigInt64Array()方法**是 util 模块的内置应用编程接口，用于对 node.js 中的 BigInt64Array 进行类型检查。

**语法:**

```js
util.types.isBigInt64Array( value )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **Value:** It is a required parameter and can be of any data type.

**返回值:**它返回一个布尔值，即如果该值是 BigInt64Array，则为真，否则为假。

下面的例子说明了在 Node.js 中使用 util . types . is initit 64 array()方法:

**例:**

```js
// Node.js program to demonstrate the   
// util.types.isBigInt64Array() Method 

// Allocating util module
const util = require('util');

// Functions to be passed as parameter
// of utiltypes.isBigInt64Array() method
var v1 = new BigInt64Array();
var v2 = new BigUint64Array();

// Printing the returned value from
// util.types.isBigInt64Array() method
console.log(util.types.isBigInt64Array(v1));
console.log(util.types.isBigInt64Array(v2));
```

**输出:**

```js
true
false

```

**例:**

```js
// Node.js program to demonstrate the   
// util.types.isBigInt64Array() Method

// Allocating util module
const util = require('util');

// Functions to be passed as parameter of
// utiltypes.isBigInt64Array() method
var v1 = new BigInt64Array();
var v2 = new BigUint64Array();

// Calling util.types.isBigInt64Array() method
if(util.types.isBigInt64Array(v1))
    console.log("The passed value is a BigInt64Array.");
else
    console.log("The passed value is not a BigInt64Array");

if(util.types.isBigInt64Array(v2))
    console.log("The passed value is a BigInt64Array.");
else
    console.log("The passed value is not a BigInt64Array");
```

**输出:**

```js
The passed value is a BigInt64Array.
The passed value is not a BigInt64Array

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ is iguing 64 array _ value](https://nodejs.org/api/util.html#util_util_types_isbigint64array_value)