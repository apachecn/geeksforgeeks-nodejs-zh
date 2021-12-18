# node . js util . types . isayarrayborfer()方法

> 原文:[https://www . geeksforgeeks . org/node-js-util-types-is anaryraybuffer-method/](https://www.geeksforgeeks.org/node-js-util-types-isanyarraybuffer-method/)

**util . types . IsYArrayBuffer()方法**是 util 模块的内置应用编程接口，用于对 node.js 中的任何内置 arrayBuffer 对象执行类型检查。

**语法:**

```js
util.types.isAnyArrayBuffer( value )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **Value:** It is a required parameter of any data type.

**返回值:**返回布尔值，即如果值是内置的 SharedArrayBuffer 或 ArrayBuffer 对象，则为真，否则为假。

下面的例子说明了在 Node.js 中使用 util . types . isayarraybuffer()方法:

**例 1:**

```js
// Node.js program to demonstrate the   
// util.types.isAnyArrayBuffer() Method 

// Allocating util module
const util = require('util');

// Printing the returned value from
// util.types.isAnyArrayBuffer() method
console.log(util.types.isAnyArrayBuffer(new ArrayBuffer()));
console.log(util.types.isAnyArrayBuffer(new SharedArrayBuffer()));
console.log(util.types.isAnyArrayBuffer(12));
console.log(util.types.isAnyArrayBuffer("geeksforgeeks"));
```

**输出:**

```js
true
true
false
false

```

**例 2:**

```js
// Node.js program to demonstrate the   
// util.types.isAnyArrayBuffer() Method 

// Allocating util module
const util = require('util');

// Printing the returned value from 
// util.types.isAnyArrayBuffer() method
if (util.types.isAnyArrayBuffer(new ArrayBuffer())) {
    console.log("Passed value is either built in "
        + "ArrayBuffer or SharedArrayBuffer ");
}
if (util.types.isAnyArrayBuffer(new SharedArrayBuffer())) {
    console.log("Passed value is either built in "
        + "ArrayBuffer or SharedArrayBuffer ");
}
```

**输出:**

```js
Passed value is either built in ArrayBuffer or SharedArrayBuffer
Passed value is either built in ArrayBuffer or SharedArrayBuffer

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isayarybuffer _ value](https://nodejs.org/api/util.html#util_util_types_isanyarraybuffer_value)