# node . js util . types . isin 32 array()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is it32 array-method/](https://www.geeksforgeeks.org/node-js-util-types-isint32array-method/)

util 模块的**util . types . Isit32 array()方法**主要是为了支持 Node.js 自身内部 API 的需求而设计的。它用于检查方法中传递的实例是否是内置的 Int32Array 实例。

**语法:**

```
util.types.isInt32Array( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何值，即任何模块的实例。

**返回值:**该方法返回一个布尔值，即如果传递的值是 Int32Array 的实例，则返回 **true** ，否则返回 **false** 。

下面的例子说明了在 Node.js 中 **util.types.isInt32Array()方法**的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// util.types.isInt32Array() method

// It includes util module
const util = require('util');

// Return false as passed instance is of map
console.log(util.types.isInt32Array(new Map()));

// Return true as passed instance is of Int32Array
console.log(util.types.isInt32Array(new Int32Array()));
```

**输出:**

```
false
true
```

**例 2:**

```
// Node.js program to demonstrate the   
// util.types.isInt32Array() method

// It includes util module
const util = require('util');

// Making an instance of Int32Array
// of size 2
var array1 = new Int32Array(2);

// Initializing the zeroth element 
array1[0] = 42;

// Returns true as passed instance is of Int32Array
console.log(util.types.isInt32Array(array1));

// Making an instance of Int32Array
var array2 = new Int32Array([21, 31]);

// Returns true as passed instance is of Int32Array
console.log(util.types.isInt32Array(array2));

// Making an instance of Int32Array
var array3 = new Int32Array([21, 31]);

// Making another instance of Int32Array by
// passing an instance of Int32Array
var array4 = new Int32Array(array3);

// Returns true as passed instance is of Int32Array
console.log(util.types.isInt32Array(array4));

// Making an instance of Int16Array of size 2
var array5 = new Int16Array(2);

// Initializing the zeroth element 
array5[0] = 10;

// Returns false as passed instance is of Int16Array
console.log(util.types.isInt32Array(array5));
```

**输出:**

```
true
true
true
false
```

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isint 32 array _ value