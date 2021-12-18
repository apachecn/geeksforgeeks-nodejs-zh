# Node.js v8。解串器. readDouble()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-反序列化-readdouble-method/](https://www.geeksforgeeks.org/node-js-v8-deserializer-readdouble-method/)

**v8。反序列化. readDouble()方法**是 v8 的内置应用编程接口。反序列化模块，用于从缓冲区读取 JS 号。用于自定义反序列化程序内部。_readHostObject()。

**语法:**

```js
v8.Deserializer.readDouble();
```

**参数:**此方法不接受任何参数。

**返回值:**该方法从缓冲区读取 JS 号并返回。

下面的例子说明了 v8 的使用。Node.js 中的反序列化器. readDouble()方法:

**示例 1:** **文件名:index.js**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeDouble() 
serializer.writeDouble(57839.83475);

// Calling v8.deserializer.readDouble() 
const deserializer = new v8.Deserializer(
            serializer.releaseBuffer());

console.log(deserializer.readDouble());
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
57839.83475

```

**示例 2:** **文件名:**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeDouble() 
console.log(serializer.releaseBuffer());
serializer.writeDouble(29698.674673);
buff = serializer.releaseBuffer();
console.log("buffer data is:");
console.log(buff);

// Calling v8.deserializer.readDouble() 
const deserializer = new v8.Deserializer(buff);
console.log("deserialized data: ");
console.log(deserializer.readDouble());
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
<Buffer >
buffer data is:
<Buffer a0 a9 d7 2d ab 00 dd 40>
deserialized data:
29698.674673

```

**参考:**T2】https://nodejs.org/api/v8.html#v8_deserializer_readdouble