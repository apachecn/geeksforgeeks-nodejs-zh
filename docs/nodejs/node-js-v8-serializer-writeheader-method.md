# Node.js v8。Serializer.writeHeader()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-serializer-write header-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writeheader-method/)

**v8。Serializer.writeHeader()方法**是 v8 的内置应用编程接口。序列化程序模块，用于写出包含序列化格式版本的标头。

**语法:**

```
v8.Serializer.writeHeader();
```

**参数:**该方法没有任何参数。

**返回值:**这个方法不返回任何东西，只向内部缓冲区写一个头。

下面的例子说明了 v8 的使用。Node.js 中的 Serializer.writeHeader()方法

**示例 1:** **文件名:index.js**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeHeader() 
console.log(serializer.releaseBuffer());
console.log(serializer.writeHeader());
console.log(serializer.releaseBuffer());
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
<Buffer >
undefined
<Buffer ff 0d>

```

**示例 2:** **文件名:**

```
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeHeader() 
console.log(serializer.writeHeader());
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
undefined

```

**参考:**T2】https://nodejs.org/api/v8.html#v8_serializer_writeheader