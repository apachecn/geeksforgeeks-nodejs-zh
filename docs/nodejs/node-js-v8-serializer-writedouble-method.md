# Node.js v8。Serializer.writeDouble()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-serializer-write double-method/](https://www.geeksforgeeks.org/node-js-v8-serializer-writedouble-method/)

**v8。Serializer.writeDouble()方法**是 v8 的内置应用编程接口。串行器模块，用于将 JS 编号值写入内部缓冲区。用于自定义序列化程序内部。_writeHostObject()。

**语法:**

```js
v8.Serializer.writeDouble( Value );
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **value:** is a required parameter, which refers to the JS number value to be written into the internal buffer.

**返回值:**这个方法不返回任何东西，而是将一个 JS 号值写入内部缓冲区。

下面的例子说明了 v8 的使用。Node.js 中的 Serializer.writeDouble()方法:

**示例 1:** **文件名:index.js**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeDouble() 
serializer.writeDouble(5783.3984);
console.log(serializer.releaseBuffer());
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
<Buffer ba da 8a fd 65 97 b6 40>

```

**示例 2:** **文件名:**

```js
// Accessing v8 module
const v8 = require('v8');
const serializer = new v8.Serializer();

// Calling v8.serializer.writeRawBytes() 
console.log(serializer.releaseBuffer());

// User defined Function
function writeDoubleData(data) {
    serializer.writeDouble(data);
    console.log(serializer.releaseBuffer());
}

// Function Call
writeDoubleData(123.44);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
<Buffer >
<Buffer 5c 8f c2 f5 28 dc 5e 40>

```

**参考:**[https://nodejs . org/API/V8 . html # V8 _ serializer _ write double _ value](https://nodejs.org/api/v8.html#v8_serializer_writedouble_value)