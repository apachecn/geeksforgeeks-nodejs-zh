# node . js util . types . isarraybuffer()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isarraybuffer-method/](https://www.geeksforgeeks.org/node-js-util-types-isarraybuffer-method/)

**util . types . isaarraybuffer()方法**是 util 模块的内置应用编程接口，用于检查 node.js 中的内置 ArrayBuffer 类型对象。

**语法:**

```js
util.types.isArrayBuffer( value )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **Value:** It is a required parameter of any data type.

**返回值:**返回一个布尔值，即如果该值是一个内置数组缓冲对象，则返回真，否则返回假。

下面的例子说明了 util.types.isArrayBuffer()方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// util.types.isArrayBuffer() Method 

// Allocating util module
const util = require('util');

// Printing the returned value from
// util.types.isArrayBuffer() method
console.log(util.types.isArrayBuffer(new ArrayBuffer()));
console.log(util.types.isArrayBuffer(new SharedArrayBuffer()));
console.log(util.types.isArrayBuffer(39));
console.log(util.types.isArrayBuffer("gfg"));
```

**输出:**

```js
true
false
false
false

```

**例:**

```js
// Node.js program to demonstrate the   
// util.types.isArrayBuffer() Method 

// Allocating util module
const util = require('util');

// Printing the returned value from 
// util.types.isArrayBuffer() method
if (util.types.isArrayBuffer(new ArrayBuffer())) {
    console.log("Passed value is built in ArrayBuffer");
}
if (util.types.isArrayBuffer(new SharedArrayBuffer())) {
    console.log("Passed value is built in ArrayBuffer");
}
```

**输出:**

```js
Passed value is built in ArrayBuffer

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isarraybbuffer _ value