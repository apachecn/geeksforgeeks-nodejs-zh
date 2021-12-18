# Node.js stringDecoder.end()方法

> 原文:[https://www . geesforgeks . org/node-js-stringdecoder-end-method/](https://www.geeksforgeeks.org/node-js-stringdecoder-end-method/)

**stringDecoder.end()方法**用于将存储在内部缓冲区中的所有剩余输入作为字符串返回。此方法确保任何不完整的 UTF-8 和 UTF-16 字符被替换为适合字符编码的替换字符。

当提供可选的缓冲区参数时，在返回剩余的缓冲区输入之前，将对数据调用一次 stringDecoder.write()方法。

**语法:**

```js
stringDecoder.end( [buffer] )
```

**参数:**该功能接受如上所述的单个参数，描述如下:

*   **缓冲区:**它是一个包含必须解码的字节的缓冲区、类型数据区或数据视图。这是一个可选参数。

**返回值:**它以字符串形式返回存储在缓冲区中的剩余输入。
下面的程序说明了 Node.js 中的 **stringDecoder.end()** 方法:

**例 1:**

## java 描述语言

```js
// Import the string_decoder module
// and get the StringDecoder class 
// using object destructuring
const { StringDecoder } = require("string_decoder");

const decoder = new StringDecoder("utf-8");

// Using the end() method
const text_one = Buffer.from("GeeksforGeeks", "utf-8");
let decoded_text = decoder.end(text_one);
console.log("Decoded Text:", decoded_text);

// The Euro Symbol is denoted using
// the bytes [0xE2, 0x82, 0xAC]

console.log("Decoding the Euro Symbol:");

// Decoding the euro symbol
// Using the write() method to
// write the first two parts
console.log(decoder.write(Buffer.from([0xE2])));
console.log(decoder.write(Buffer.from([0x82])));

// Finishing the symbol using the end() method
// with that gives an additional call to write()
// using the last part of the buffer
console.log(decoder.end(Buffer.from([0xAC])));
```

**输出:**

```js
Decoded Text: GeeksforGeeks
Decoding the Euro Symbol:

€
```

**例 2:**

## java 描述语言

```js
// Import the string_decoder module
// and get the StringDecoder class 
// using object destructuring
const { StringDecoder } = require("string_decoder");
const decoder = new StringDecoder("utf-8");
// The Cent Symbol is denoted using
// Buffer.from([0xc2, 0xa2])

// Decoding the complete cent symbol from buffer
let cent_symbol = Buffer.from([0xc2, 0xa2]);
let cent_symbol_out = decoder.end(cent_symbol);
console.log("Complete Cent Symbol:", cent_symbol_out);

// Decoding incomplete cent symbol using
// Buffer.write() method
cent_symbol = Buffer.from([0xc2]);
cent_symbol_out = decoder.write(cent_symbol);
console.log("Cent Symbol using write():",
                       cent_symbol_out);

// Decoding incomplete cent symbol
// using Buffer.end() method
cent_symbol = Buffer.from([0xc2]);
cent_symbol_out = decoder.end(cent_symbol);
console.log("Cent Symbol using end():",
                     cent_symbol_out);
```

**输出:**

```js
Complete Cent Symbol: ¢
Cent Symbol using write():
Cent Symbol using end(): ??
```

**参考:**[https://nodejs . org/API/string _ decoder . html # string _ decoder _ stringdecoder _ end _ buffer](https://nodejs.org/api/string_decoder.html#string_decoder_stringdecoder_end_buffer)