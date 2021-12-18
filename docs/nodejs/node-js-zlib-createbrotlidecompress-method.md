# node . js zlib . createbrotlidecompress()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-createbrotlidecompress-method/](https://www.geeksforgeeks.org/node-js-zlib-createbrotlidecompress-method/)

**zlib.createBrotliDecompress()方法**是 zlib 模块的内置应用程序编程接口，用于创建新的 BrotliDecompress 对象。

**语法:**

```
zlib.createBrotliDecompress( options )
```

**参数:**该方法接受单参数**选项**，这是一个保存 zlib 选项的可选参数。

**返回值:**返回一个新的 BrotliDecompress 对象。

以下示例说明了在 Node.js 中使用 **zlib.createBrotliDecompress()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// createBrotliDecompress() method

// Including zlib module
var zlib = require('zlib');

// Calling brotliCompress function to compress data
zlib.brotliCompress('Nidhi', function(err, data) {
  if (err) { 
    return console.log('err', err);
  }

  // Calling createBrotliDecompress method
  // to decompress the data again
  var gunzip = zlib.createBrotliDecompress();
  gunzip.write(data);
  gunzip.on('data', function (data) {
      console.log(data.toString());
  });
});
```

**输出:**

```
Nidhi

```

**例 2:**

```
// Node.js program to demonstrate the     
// createBrotliDecompress() method

// Including zlib module
var zlib = require('zlib');

// Calling brotliCompress function to compress data
zlib.brotliCompress('CS-Portal!', function(err, data) {
  if (err) { 
    return console.log('err', err);
  }

  // Calling createBrotliDecompress method
  // to decompress the data again
  var gunzip = zlib.createBrotliDecompress();
  gunzip.write(data);
  gunzip.on('data', function (data) {
      console.log(data.toString('base64'));
  });
});
```

**输出:**

```
Q1MtUG9ydGFsIQ==

```

**参考:**[https://nodejs . org/API/zlib . html # zlib _ create Bromley press _ options](https://nodejs.org/api/zlib.html#zlib_zlib_createbrotlidecompress_options)