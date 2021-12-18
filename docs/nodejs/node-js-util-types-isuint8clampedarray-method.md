# node . js util . types . isint8 clampedarray()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-ISU int8 clampedarray-method/](https://www.geeksforgeeks.org/node-js-util-types-isuint8clampedarray-method/)

**util . types . isunit8 clampedarray()方法**是 util 模块的内置应用编程接口，主要是为了支持 Node.js 自身内部 API 的需求而设计的。

**util . types . isint8 clampedarray()方法**用于检查给定值是否为无符号 8 位钳制整数数组。

**语法:**

```
util.types.isUint8ClampedArray( value )
```

**参数:**该函数接受如上所述的单个参数，如下所述:

*   **Value:** This value will be checked as an 8-bit unsigned clamped integer array.

**返回值:**如果传递的值是无符号 8 位钳制整数数组，则返回布尔值，即**真**，否则返回**假**。

下面的例子说明了 Node.js 中的**util . types . isint8 clampedarray()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// util.types.isUint8ClampedArray() method

// Import the util module
const util = require('util');

// Checking for a unsigned 8-bit
// clamped integer array
isUint8ClampedArr = util.types.isUint8ClampedArray(
                    new Uint8ClampedArray());

console.log("Object is Unsigned 8-bit clamped array"
                  + " object:", isUint8ClampedArr);

// Checking for a unsigned 8-bit
// unclamped integer array
isUint8ClampedArr = util.types.isUint8ClampedArray(
                    new Uint8Array());

console.log("Object is Unsigned 8-bit clamped"
                  + " array object:", isUint8ClampedArr);

// Checking for a integer array
isUint8ClampedArr = util.types.isUint8ClampedArray(
                  new Int8Array());

console.log("Object is Unsigned 8-bit clamped "
                  + "array object:", isUint8ClampedArr);
```

**输出:**

```
Object is Unsigned 8-bit clamped array object: true
Object is Unsigned 8-bit clamped array object: false
Object is Unsigned 8-bit clamped array object: false
```

**例 2:**

```
// Node.js program to demonstrate the
// util.types.isUint8ClampedArray() method

// Import the util module
const util = require('util');

// Checking a big unsigned 64-bit
// integer array
let UintClampedArr = 
    new Uint8ClampedArray([0, 128, 1024, 2054]);

console.log(UintClampedArr);

isUint8ClampedArr = 
    util.types.isUint8ClampedArray(UintClampedArr);

console.log("Object is Unsigned 8-bit clamped"
            + " array object:", isUint8ClampedArr);

// Checking a unsigned 32-bit integer array
let unsigned32Arr = new Uint32Array([4, 25, 128]);
console.log(unsigned32Arr);

isUint8ClampedArr = 
    util.types.isUint8ClampedArray(unsigned32Arr);
console.log("Object is Unsigned 8-bit clamped"
            + " array object:", isUint8ClampedArr);

// Checking a big signed 64-bit integer array
let bigSigned64Arr = new BigInt64Array([16n, 25n, 128n]);
console.log(bigSigned64Arr);

isUint8ClampedArr = 
    util.types.isUint8ClampedArray(bigSigned64Arr);
console.log("Object is Unsigned 8-bit clamped"
            + " array object:", isUint8ClampedArr);
```

**输出:**

```
Uint8ClampedArray [ 0, 128, 255, 255 ]
Object is Unsigned 8-bit clamped array object: true
Uint32Array [ 4, 25, 128 ]
Object is Unsigned 8-bit clamped array object: false
BigInt64Array [ 16n, 25n, 128n ]
Object is Unsigned 8-bit clamped array object: false
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isint 8 clampedarray _ value](https://nodejs.org/api/util.html#util_util_types_isuint8clampedarray_value)