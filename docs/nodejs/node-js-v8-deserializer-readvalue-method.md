# Node.js v8。反序列化程序读取值()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-反序列化-readvalue-method/](https://www.geeksforgeeks.org/node-js-v8-deserializer-readvalue-method/)

**v8。Deserializer.readValue()方法**是 v8 的内置应用编程接口。反序列化模块，用于从缓冲区中的序列化数据中读取 JS 值。

**语法:**

```js
v8.Deserializer.readValue();
```

**参数:**此方法不接受任何参数。

**返回值:**该方法从缓冲区中存在的序列化表示中读取 JS 值，并在成功读取时返回。

下面的例子说明了 v8 的使用。Node.js 中的反序列化器. readValue()方法:

**示例 1:** **文件名:index.js**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeValue() 
console.log(serializer.writeValue("GeeksforGeeks"));

// Calling v8.deserializer.readValue() 
const deserializer = new v8.Deserializer(
            serializer.releaseBuffer());

console.log(deserializer.readValue());
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
true
GeeksforGeeks

```

**示例 2:** **文件名:**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeValue() 
console.log(serializer.writeValue(839475.3495));
buff = serializer.releaseBuffer();
console.log("buffer data is:");
console.log(buff);

// Calling v8.deserializer.readValue() 
const deserializer = new v8.Deserializer(buff);

console.log("deserialized data: " 
        + deserializer.readValue());
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
true
buffer data is:
<Buffer 4e fc a9 f1 b2 66 9e 29 41>
deserialized data: 839475.3495

```

**参考资料:**[https://nodejs . org/API/V8 . html # V8 _ 取消初始化 _readvalue](https://nodejs.org/api/v8.html#v8_deserializer_readvalue)