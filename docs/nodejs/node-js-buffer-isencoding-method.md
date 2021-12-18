# Node.js Buffer.isEncoding()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-isen coding-method/](https://www.geeksforgeeks.org/node-js-buffer-isencoding-method/)

**Buffer.isEncoding()方法**检查给定的编码是否被支持。此方法返回真或假的布尔值。

**语法:**

```js
Buffer.isEncoding( encoding )
```

**参数:**该方法接受单参数**编码**，保存编码名称。支持的编码有 ascii、utf8、utf16le、ucs2、base64、latin1、二进制等。

**例 1:**

```js
// Node.js program to demonstrate the 
// Buffer.isEncoding() method 

// Displays whether the given encoding 
// is supported or not
console.log(Buffer.isEncoding('utf8'));
console.log(Buffer.isEncoding('utf16le'));
console.log(Buffer.isEncoding('ascii'));
console.log(Buffer.isEncoding('asciivalue'));
console.log(Buffer.isEncoding('base64'));
console.log(Buffer.isEncoding('basename'));
```

**输出:**

```js
true
true
true
false
true
false

```

**例 2:**

```js
// Node.js program to demonstrate the 
// Buffer.isEncoding() method 

// Displays whether the given encoding 
// is supported or not
console.log(Buffer.isEncoding('ucs2'));
console.log(Buffer.isEncoding('name'));
console.log(Buffer.isEncoding('binary'));
console.log(Buffer.isEncoding('latin1'));
console.log(Buffer.isEncoding('base64'));
```

**输出:**

```js
true
false
true
true
true

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buffer _ class _ method _ buffer _ isencoding _ encoding](https://nodejs.org/api/buffer.html#buffer_class_method_buffer_isencoding_encoding)