# node . js util . types . isuit 8 array()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-ISU int8 array-method/](https://www.geeksforgeeks.org/node-js-util-types-isuint8array-method/)

util 模块的**util . types . isuit 8 array()方法**，主要是为了支持 Node.js 自带的内部 API 的需求而设计的。它用于检查方法中传递的实例是否是内置的 Uint8Array 实例。

**语法**

```
util.types.isUint8Array( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何值，即任何模块的实例。

**返回值:**该方法返回一个布尔值，即如果传递的值是 Uint8Array 的实例，则返回 **true** ，否则返回 **false** 。

下面的例子说明了在 Node.js 中使用**util . types . isint8 array()方法**:

**例 1:**

```
// Node.js program to demonstrate the    
// util.types.isUint8Array() method 

// It includes util module 
const util = require('util'); 

// Return false as passed instance is of set 
console.log(util.types.isUint8Array(new Set())); 

// Return true as passed instance is of Uint8Array 
console.log(util.types.isUint8Array(new Uint8Array())); 
```

**输出:**

```
false
true
```

**例 2:**

```
// Node.js program to demonstrate the    
// util.types.isUint8Array() method 

// It includes util module 
const util = require('util'); 

// Making an instance of Uint8Array 
// of size 2 
var array1 = new Uint8Array(2); 

// Initializing the zeroth element  
array1[0] = 42; 

// Returns true as passed instance
// is of Uint8Array 
console.log(util.types.isUint8Array(array1)); 

// Making an instance of Uint8Array 
var array2 = new Uint8Array([21, 31]); 

// Returns true as passed instance
// is of Uint8Array 
console.log(util.types.isUint8Array(array2)); 

// Making an instance of Uint8Array 
var array3 = new Uint8Array([21, 31]); 

// Making another instance of Uint8Array by 
// passing an instance of Uint8Array 
var array4 = new Uint8Array(array3); 

// Returns true as passed instance
// is of Uint8Array 
console.log(util.types.isUint8Array(array4)); 

// Making an instance of Int16Array of size 2 
var array5 = new Int16Array(2); 

// Initializing the zeroth element  
array5[0] = 10; 

// Returns false as passed instance
// is of Int16Array 
console.log(util.types.isUint8Array(array5)); 
```

**输出:**

```
true
true
true
false
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isint 8 array _ value](https://nodejs.org/api/util.html#util_util_types_isuint8array_value)