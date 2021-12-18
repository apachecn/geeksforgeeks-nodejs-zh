# Base64 编解码是如何在 node.js 中完成的？

> 原文:[https://www . geesforgeks . org/how-base64-编码和解码在节点中完成-js/](https://www.geeksforgeeks.org/how-base64-encoding-and-decoding-is-done-in-node-js/)

Base64 编码和解码可以在 Node.js 中使用 Buffer 对象完成。

**将原始字符串编码为 base64:**node . js 中的 Buffer 类可用于将字符串转换为一系列字节。这可以使用 **Buffer.from()** 方法来完成，该方法接受要转换的字符串和字符串的当前编码。这种编码可以指定为“utf8”。

然后可以使用 **toString()** 方法将转换后的字节作为 base64 返回。此方法接受指定转换期间所需编码的参数。在这种情况下，“base64”被指定为要使用的编码。因此，此方法将任何字符串转换为 base64 格式。

**语法:**

```js
// Create buffer object, specifying utf8 as encoding
let bufferObj = Buffer.from(originalString, "utf8");

// Encode the Buffer as a base64 string
let base64String = bufferObj.toString("base64");

```

**示例:**

```js
// The original utf8 string
let originalString = "GeeksforGeeks";

// Create buffer object, specifying utf8 as encoding
let bufferObj = Buffer.from(originalString, "utf8");

// Encode the Buffer as a base64 string
let base64String = bufferObj.toString("base64");

console.log("The encoded base64 string is:", base64String);
```

**输出:**

```js
The encoded base64 string is: R2Vla3Nmb3JHZWVrcw==
```

**将 base64 解码为原始字符串:**缓冲区也可用于将 base64 字符串转换回 utf8 编码。 **Buffer.from()** 方法再次用于将 base64 字符串转换回字节，但是这次将当前编码指定为“base64”。

然后可以使用 **toString()** 方法将转换后的字节作为原始 utf8 字符串返回。在这种情况下，“utf8”被指定为要使用的编码。因此，此方法将 base64 转换为其原始 utf9 格式。

**语法:**

```js
// Create a buffer from the string
let bufferObj = Buffer.from(base64string, "base64");

// Encode the Buffer as a utf8 string
let decodedString = bufferObj.toString("utf8");
```

**示例:**

```js
// The base64 encoded input string
let base64string = "R2Vla3Nmb3JHZWVrcw==";

// Create a buffer from the string
let bufferObj = Buffer.from(base64string, "base64");

// Encode the Buffer as a utf8 string
let decodedString = bufferObj.toString("utf8");

console.log("The decoded string:", decodedString);
```

**输出:**

```js
The decoded string: GeeksforGeeks
```