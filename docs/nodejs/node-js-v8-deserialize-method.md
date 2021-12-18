# Node.js v8 .反序列化()方法

> 原文:[https://www . geesforgeks . org/node-js-V8-反序列化-method/](https://www.geeksforgeeks.org/node-js-v8-deserialize-method/)

**v8 .反序列化()方法**是 v8 模块的内置应用编程接口，用于使用默认反序列化程序将缓冲的数据反序列化为 JS 值。

**语法:**

```
v8.deserialize( buffer );
```

**参数:**该方法接受一个参数，如上所述，如下所述:

*   **Buffer:** This is a required parameter, Buffer/TypedArray/DataView, which refers to the buffered data to be deserialized.

**返回值:**此方法在反序列化缓冲的数据后返回 JS 值。

下面的例子说明了在 Node.js 中使用 v8.deserialize()方法

**示例 1:** **文件名:index.js**

```
// Accessing v8 module
const v8 = require('v8');

// Calling v8.deserialize() 
console.log(v8.deserialize(v8.serialize("geeksforgeeks")));
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
geeksforgeeks

```

**示例 2:** **文件名:**

```
// Accessing v8 module
const v8 = require('v8');

// Calling v8.deserialize() 
deserialized_data = v8.deserialize(v8.serialize("abcdefg"));
console.log("\nDeserialized data is ");
console.log(deserialized_data);

deserialized_data = v8.deserialize(v8.serialize(58375693));
console.log("\nDeserialized data is ");
console.log(deserialized_data);

deserialized_data = v8.deserialize(v8.serialize(73847.0234));
console.log("\nDeserialized data is ");
console.log(deserialized_data);

deserialized_data = v8.deserialize(v8.serialize('Geek'));
console.log("\nDeserialized data is ");
console.log(deserialized_data);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Deserialized data is
abcdefg

Deserialized data is
58375693

Deserialized data is
73847.0234

Deserialized data is
Geek

```

**参考:**T2】https://nodejs.org/api/v8.html#v8_v8_deserialize_buffer