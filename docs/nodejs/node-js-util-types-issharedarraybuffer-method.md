# node . js | util . types . issharedraybuffer()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-issharedraybuffer-method/](https://www.geeksforgeeks.org/node-js-util-types-issharedarraybuffer-method/)

util 模块的**util . types . IssharedrayBuffer()方法**主要是为了支持 Node.js 自己的内部 API 的需求而设计的。它用于检查方法中传递的实例是否是内置的 SharedArrayBuffer 实例。

**语法:**

```js
util.types.isSharedArrayBuffer( *value* )
```

**参数:**该方法接受单个参数**值**，该值保存任何值，即任何模块的实例。

**返回值:**如果传递的值是 SharedArrayBuffer 的实例，该方法返回一个布尔值，即**真**，否则返回**假**。

以下示例说明了在 Node.js 中使用**util . types . issharedraybuffer()方法**:

**例 1:**

```js
// Node.js program to demonstrate the    
// util.types.isSharedArrayBuffer() method 

// It includes util module 
const util = require('util'); 

// Return true as passed instance
// is of SharedArrayBuffer 
console.log(util.types.isSharedArrayBuffer(
                 new SharedArrayBuffer())); 

// Return false as passed instance
// is of Int32Array 
console.log(util.types.isSharedArrayBuffer(
                 new Int32Array())); 

// Return false as the passed instance is
// of ArrayBuffer, not SharedArrayBuffer
console.log(util.types.isSharedArrayBuffer(
                 new ArrayBuffer()));
```

**输出:**

```js
true
false
false
```

**例 2:**

```js
// Node.js program to demonstrate the    
// util.types.isSharedArrayBuffer() method 

// It includes util module 
const util = require('util'); 

// making an  instance of SharedArrayBuffer
// of size 1024
var sab = new SharedArrayBuffer(1024);

// Return true as passed instance is
// of SharedArrayBuffer 
console.log(util.types.isSharedArrayBuffer(sab)); 

// Return true as slice method return new
// instance of sharedArrayBuffer 
console.log(util.types.isSharedArrayBuffer(
               sab.slice(100, 199)));
```

**输出:**

```js
true
true
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ issshared array buffer _ value](https://nodejs.org/api/util.html#util_util_types_issharedarraybuffer_value)