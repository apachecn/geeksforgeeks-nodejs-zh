# node . js util . types . isint16 array()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isuit 16 array-method/](https://www.geeksforgeeks.org/node-js-util-types-isuint16array-method/)

***util . types . Isint16 array()***(在 v10.0.0 中添加)方法是 util 模块的一个内置应用编程接口，用于检查传递的值在 node.js 中是否属于类型 *Uint16Array* ，如果传递的值属于类型“Uint16Array”，则返回“真”，否则返回“假”。

**语法:**

```js
const util = require('util');
util.types.isUint16Array( value )

```

**参数:**该方法接受如上所述的单个参数，如下所述。

*   **值** < *任意* > **:** 它是接受任意变量、类、函数、对象或 JavaScript 原语或任意数据类型的必需参数。

**返回值** < *布尔值* > **:这返回一个布尔值。如果传递的值属于“Uint16Array”类型，则返回“true”，否则返回“false”。**

下面的例子说明了在 Node.js 中 util . types . isuit 16 array()方法的使用

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the
// util.types.isUint16Array() method

// Using require to access util module
const util = require('util');
const { types } = require('util');

// Passing ArrayBuffer as parameter
console.log("1.>", util.types.isUint16Array(
        new ArrayBuffer()));
// Returns false

// Passing Uint16Array with argument as parameter
console.log("2.>", util.types.isUint16Array(
        new Uint16Array(60)));
// Returns true

// Passing Uint32Array as parameter
console.log("3.>", util.types.isUint16Array(
        new Uint16Array(500)));
// Returns true

// Passing Uint32Array as parameter
console.log("4.>", types.isUint16Array(
        new Uint32Array()));
// Returns false

// Passing data as parameter from 0 to 4294967295
console.log("5.>", types.isUint16Array(
        new Uint16Array([1, 5, 8, 1, 95])));
// Returns true

// Passing Float64Array as parameter
console.log("6.>", util.types.isUint16Array(
        new Float64Array(64)));
// Returns false

// Passing Int8Array as parameter
console.log("7.>", util.types.isUint16Array(
        new Int8Array(8)));
// Returns false
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 1.>假
> 
> 2.>真
> 
> 3.>真
> 
> 4.>假
> 
> 5.>真
> 
> 6.>假
> 
> 7.>假

**示例 2:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// util.types.isUint16Array() method 

// Using require to access util module 
const util = require('util');
const { types } = require('util');

// Passing BigInt64Array as parameter
console.log("1.>", util.types.isUint16Array(
        new BigInt64Array()));
// Returns false

// Passing BigUint64Array as parameter
console.log("2.>", util.types.isUint16Array(
        new BigUint64Array()));
// Returns false

// Passing Float32Array as parameter
console.log("3.>", util.types.isUint16Array(
        new Float32Array()));
// Returns false

// Passing Int8Array as parameter
console.log("4.>", util.types.isUint16Array(
        new Int8Array()));
// Returns false

// Passing Int16Array as parameter
console.log("5.>", util.types.isUint16Array(
        new Int16Array()));
// Returns false

// Passing Uint8Array as parameter
console.log("7.>", types.isUint16Array(
        new Uint8Array()));
// Returns false

// Passing Float64Array as parameter
console.log("8.>", types.isUint16Array(
        new Float64Array()));
// Returns false

var var1 = new Uint16Array();
var var2 = new Int16Array();

// Calling util.types.isUint16Array() method 
if (util.types.isUint16Array(var1))
    console.log("Yes, the value is a isUint16Array.");
else
    console.log("No, provided value is not a isUint16Array");

// Calling util.types.isUint16Array() method 
if (util.types.isUint16Array(var2))
    console.log("Yes, the value is a isUint16Array.");
else
    console.log("No, provided value is not a isUint16Array");
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 1.>假
> 
> 2.>假
> 
> 3.>假
> 
> 4.>假
> 
> 5.>假
> 
> 6.>假
> 
> 7.>假
> 
> 8.>假
> 
> 是的，该值是一个 isint16 数组。
> 
> 否，提供的值不是 isint16 数组

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isint 16 array _ value](https://nodejs.org/api/util.html#util_util_types_isuint16array_value)