# Node.js v8。Serializer.writeUint64()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-serializer-writeuint 64-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writeuint64-method/)

**v8。Serializer.writeUint64()方法**是 v8 的内置应用编程接口。串行器模块，用于将原始 64 位整数值拆分为高 32 位整数和低 32 位整数，写入内部缓冲区。用于自定义序列化程序内部。_writeHostObject()方法。

**语法:**

```
v8.Serializer.writeUint64(Value_high, Value_low);
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Value _ high:** It is a required parameter, which refers to the higher 32 bits of the 64-bit integer to be written into the internal buffer.
*   **Value _ low:** is a required parameter, which refers to the lower 32 bits of the 64-bit integer written into the internal buffer.

**返回值:**此方法不返回任何内容，而是将原始的 64 位整数值写入内部缓冲区。

下面的例子说明了 v8 的使用。Node.js 中的 Serializer.writeUint64()方法:

**例 1:**

**文件名:**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint64() method
// Nothing is returned so, this should 
// print undefined
console.log(serializer.writeUint64(5783, 78374));
console.log(serializer.releaseBuffer());
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
undefined
<Buffer a6 e4 84 80 f0 d2 05>

```

**例 2:**

**文件名:**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint64() 
console.log(serializer.releaseBuffer());
serializer.writeUint64(29698, 3847);
console.log(serializer.releaseBuffer());

// Trying to write two 64 bit numbers
// one after another
serializer.writeUint64(29698, 3847);
serializer.writeUint64(29698, 3847);
console.log(serializer.releaseBuffer());

// Reading after write
// Calling v8.serializer.writeUint64() 
serializer.writeUint64(6783, 348072);

// Calling v8.deserializer.readUint64() 
const deserializer = new 
    v8.Deserializer(serializer.releaseBuffer());
console.log(deserializer.readUint64());
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
<Buffer >
<Buffer 87 9e 80 80 a0 80 1d>
<Buffer 87 9e 80 80 a0 80 1d 87 9e 80 80 a0 80 1d>
[ 6783, 348072 ]

```

**参考:**[https://nodejs . org/API/V8 . html # V8 _ serializar _ writeuint 64 _ hi _ lo](https://nodejs.org/api/v8.html#v8_serializer_writeuint64_hi_lo)