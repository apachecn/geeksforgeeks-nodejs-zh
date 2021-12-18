# Node.js stringDecoder.write()方法

> 原文:[https://www . geesforgeks . org/node-js-stringdecoder-write-method/](https://www.geeksforgeeks.org/node-js-stringdecoder-write-method/)

**stringDecoder.write()方法**用于从给定的缓冲区返回解码后的字符串，类型为 dArray 或 DataView。此方法还确保从返回的字符串中省略缓冲区末尾的任何不完整的多字节字符。这些字符存储在内部缓冲区中，以便下次调用`stringDecoder.write()`或`stringDecoder.end()`方法时使用。

**语法:**

```js
stringDecoder.write( buffer )
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **Buffer:** It is a buffer, type data or data view containing bytes that must be decoded.

**返回值:**返回从给定缓冲区解码的字符串。

下面的程序说明了 Node.js 中的 **stringDecoder.write()** 方法:

**例 1:**

```js
// Node.js program to demonstrate the   
// stringDecoder.write() Method 

// Import the string_decoder module
// and get the StringDecoder class 
// using object destructuring
const { StringDecoder } = require("string_decoder");

// Create a new instance of the decoder
const decoder = new StringDecoder("utf-8");

const text_one = Buffer.from("GeeksforGeeks", "utf-8");
let decoded_text = decoder.write(text_one);
console.log("Decoded Text:", decoded_text);
```

**输出:**

```js
Decoded Text: GeeksforGeeks
```

**例 2:**

```js
// Node.js program to demonstrate the   
// stringDecoder.write() Method 

// Import the string_decoder module
// and get the StringDecoder class 
// using object destructuring
const { StringDecoder } = require("string_decoder");

// Create a new instance of the decoder
const decoder = new StringDecoder("utf-8");

// Decoding text using hex from buffer
const hex_text = new Buffer.from(
      "4765656B73666F724765656B73", "hex");
let decoded_hex_text = decoder.write(hex_text);
console.log("Decoded Text Hex:", decoded_hex_text);

// Decoding text using base64 from buffer
const base64_text = new Buffer.from(
      "R2Vla3Nmb3JHZWVrcw==", "base64");
let decoded_base64_text = decoder.write(base64_text);
console.log("Decoded Text Base64:", decoded_base64_text);

// Decoding the cent symbol from buffer
const cent_symbol = Buffer.from([0xc2, 0xa2]);
let cent_symbol_out = decoder.write(cent_symbol);
console.log("Cent Symbol:", cent_symbol_out);
```

**输出:**

```js
Decoded Text Hex: GeeksforGeeks
Decoded Text Base64: GeeksforGeeks
Cent Symbol: ¢
```

**参考:**T2【https://nodejs . org/API/string _ decoder . html # string _ decoder _ string decoder _ write _ buffer