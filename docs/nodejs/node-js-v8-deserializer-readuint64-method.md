# Node.js v8。解串器. readUint64()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-反序列化程序-readuint64-method/](https://www.geeksforgeeks.org/node-js-v8-deserializer-readuint64-method/)

**v8。反序列化程序 readUint64()方法**是 v8 的内置应用编程接口。反序列化模块，用于从缓冲区中读取原始的 64 位无符号整数值，作为 32 位整数的数组，高 32 位和低 32 位分开。用于自定义反序列化程序内部。_readHostObject()。

**语法:**

```
v8.Deserializer.readUint64();
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法从缓冲区中读取原始的 64 位无符号整数值，作为一个由两个 32 位整数组成的数组，高 32 位和低 32 位分开，然后返回。

下面的例子说明了 v8 的使用。Node.js 中的反序列化器. readUint64()方法:

**示例 1:** **文件名:index.js**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint64() 
serializer.writeUint64(6783, 348072);

// Calling v8.deserializer.readUint64() 
const deserializer = new v8.Deserializer(
            serializer.releaseBuffer());

console.log(deserializer.readUint64());
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
[ 6783, 348072 ]

```

**示例 2:** **文件名:**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeUint64() 
serializer.writeUint64(29698, 34752);
buff = serializer.releaseBuffer();
console.log("buffer data is:");
console.log(buff);

// Calling v8.deserializer.readUint64() 
const deserializer = new v8.Deserializer(buff);
data = deserializer.readUint64();
console.log("higher 32-bits=%d and lower "
        + "32-bits=%d ", data[0], data[1]);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
buffer data is:
<Buffer c0 8f 82 80 a0 80 1d>
higher 32-bits=29698 and lower 32-bits=34752

```

**参考资料:**[https://nodejs . org/API/V8 . html # V8 _ disriar _ readuint 64](https://nodejs.org/api/v8.html#v8_deserializer_readuint64)