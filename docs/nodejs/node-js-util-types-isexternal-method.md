# node . js util . types . isexternal()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isexternal-method/](https://www.geeksforgeeks.org/node-js-util-types-isexternal-method/)

**util.types.isExternal()方法**是 util 模块的内置应用编程接口，用于检查该值是否是 node.js 中的本机外部值。

**语法:**

```
util.types.isExternal( value )
```

**参数:**该方法接受如上所述和如下所述的单个参数。

*   **Value:** It is a required parameter of any data type.

**返回值:**这将返回一个布尔值，如果该值是本机外部值，则为真，否则为假。

下面的例子说明了 util.types.isExternal()方法在 Node.js 中的使用:

**例 1:**

## Javascript

```
// Node.js program to demonstrate the
// util.types.isExternal() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter
// of util.types.isExternal() method
var v1 = new Date();
const { JSStream } = process.binding('js_stream');
const external = (new JSStream())._externalStream;

// Printing the returned value from
// util.types.isExternal() method

console.log(util.types.isExternal(v1));
console.log(util.types.isExternal(external));
console.log(util.types.isExternal(0));
console.log(util.types.isExternal(new String('foo')));
```

**输出:**

```
false
true
false
false
```

**例二:**

## Javascript

```
// Node.js program to demonstrate the
// util.types.isExternal() Method

// Allocating util module
const util = require('util');

// Value to be passed as parameter
// of util.types.isExternal() method
var v1 = new Date();
const { JSStream } = process.binding('js_stream');
const ext = (new JSStream())._externalStream;
var str = new String('Geeks')

// Calling
// util.types.isExternal() method
if (util.types.isExternal(v1))
    console.log("It is a native External value.");
else
    console.log("It is not a native External value.");

if (util.types.isExternal(ext))
    console.log("It is a native External value.");
else
    console.log("It is not a native External value.");

if (util.types.isExternal(0))
    console.log("It is a native External value.");
else
    console.log("It is not a native External value.");

if (util.types.isExternal(str))
    console.log("It is a native External value.");
else
    console.log("It is not a native External value.");
```

**输出:**

```
It is not a native External value.
It is a native External value.
It is not a native External value.
It is not a native External value.
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isexternal _ value](https://nodejs.org/api/util.html#util_util_types_isexternal_value)