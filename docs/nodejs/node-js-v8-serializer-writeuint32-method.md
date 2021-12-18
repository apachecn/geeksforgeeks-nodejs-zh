# Node.js v8。Serializer.writeUint32()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-serializer-writeuint32-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint32-method/)

**v8。Serializer.writeUint32()方法**是 v8 的内置应用编程接口。序列化程序模块，用于将原始 32 位整数值写入内部缓冲区。用于自定义序列化程序内部。_writeHostObject()。

**语法:**

```
v8.Serializer.writeUint32( value );
```

**参数:**该方法接受如上所述和如下所述的单个参数。

*   **Value:** is a required parameter, which refers to a 32-bit integer written into the internal buffer.

**返回值:**这个方法不返回任何东西，而是将一个原始的 32 位整数值写入内部缓冲区。

下面的例子说明了 v8 的使用。Node.js 中的 Serializer.writeUint32()方法:

**例 1:**

**文件名:**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint32() 
// The undefined will be logged in 
// console as this function does not
// return anything
console.log(serializer.writeUint32(5783));
console.log(serializer.releaseBuffer());
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Undefined
<Buffer 97 2d>

```

**例 2:**

**文件名:**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint32() 
console.log(serializer.releaseBuffer());
serializer.writeUint32(29698);
console.log(serializer.releaseBuffer());

// Writing two 32 bits number one
// after another
console.log("writing two 32 bits "
    + "number one after another");

serializer.writeUint32(29698);
serializer.writeUint32(29698);
console.log(serializer.releaseBuffer());

console.log("reading after write");

// Calling v8.serializer.writeUint32() 
serializer.writeUint32(5783);

// Calling v8.deserializer.readUint32() 
const deserializer = new 
    v8.Deserializer(serializer.releaseBuffer());
console.log(deserializer.readUint32());
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
<Buffer >
<Buffer 82 e8 01>
writing two 32 bits number one after another
<Buffer 82 e8 01 82 e8 01>
reading after write
5783

```

**参考:**T2【https://nodejs . org/API/V8 . html # V8 _ serializer _ writeuint32 _ value