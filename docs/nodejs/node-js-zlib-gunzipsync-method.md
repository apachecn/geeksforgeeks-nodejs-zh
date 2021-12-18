# Node.js zlib.gunzipSync()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-gunzipsync-method/](https://www.geeksforgeeks.org/node-js-zlib-gunzipsync-method/)

**zlib.gunzipSync()方法**是 zlib 模块的一个内置应用编程接口，用于使用 Gunzip 解压缩一大块数据。

**语法:**

```
zlib.gunzipSync( buffer, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **哥哥哥哥哥哥::t1]嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨嗨 buffer typed array data view array buffer 字符串。**
*   **Option:** This parameter stores the zlib option value.

**返回值:**用 Gunzip 返回数据块。

下面的例子说明了在 Node.js 中使用 **zlib.gunzipSync()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// zlib.gunzipSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling gzipSync method
var gzi = zlib.gzipSync(input);

// Calling gunzipSync method
var decom = zlib.gunzipSync(
    new Buffer.from(gzi)).toString();

console.log(decom);
```

**输出:**

```
Nidhi
```

**例 2:**

```
// Node.js program to demonstrate the     
// zlib.gunzipSync() method  

// Including zlib module
var zlib = require('zlib');

// Declaring input and assigning
// it a value string
var input = "Nidhi";

// Calling gzipSync method
var gzi = zlib.gzipSync(input).toString('hex');

// Calling gunzipSync method
var decom = zlib.gunzipSync(new Buffer.from(
        gzi, 'hex')).toString('base64');

console.log(decom);
```

**输出:**

```
TmlkaGk=

```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ gunzipsync _ buffer _ options](https://nodejs.org/api/zlib.html#zlib_zlib_gunzipsync_buffer_options)