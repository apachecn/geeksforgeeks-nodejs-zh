# node . js zlib . bytes written Property

> 原文:[https://www . geesforgeks . org/node-js-zlib-bytes written-property/](https://www.geeksforgeeks.org/node-js-zlib-byteswritten-property/)

**zlib . Byteswrited 属性**是 zlib 模块的一个应用程序编程接口，用于指定在字节被处理(压缩或解压缩，对于派生类来说是合适的)之前写入引擎的字节数。

**语法:**

```
zlib.bytesWritten
```

**返回值:**返回写入引擎的字节数。

下面的例子说明了在 Node.js 中使用**zlib . bytes writed 方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// zlib.bytesWritten Property

// Including assert and zlib 
// module
var zlib = require('zlib');
var assert = require('assert');

// Input to be written
const input = Buffer.from('0123456789012345678901');

// Calling deflate method
zlib.deflate(input, (err, deflatedBuffer) => {
  assert(!err);

  // Declaring buffer and numberRead
  var numberRead = 0;
  var buffers = [];

  // Creating a zip object
  var stream = zlib.createGzip()

    // Data event
    .on('data', function(chunk) {
     buffers.push(chunk);
     numberRead += chunk.length;
    })

    // end event
    .on('end', function() {

      // Calling bytesWritten property
      console.log(stream.bytesWritten);

      })
    .end(deflatedBuffer);
});
```

**输出:**

```
21

```

**例 2:**

```
// Node.js program to demonstrate the     
// zlib.bytesWritten property

// Including zlib module
var zlib = require('zlib');

// Input to be written
const input = Buffer.from('NidhiSingh1352');

// Calling deflateRaw method
zlib.deflateRaw(input, (err, buffer) => {

  // Creating a Deflate object
  var zlibs = zlib.Deflate()

    // Data event
    .on('data', function(chunk) {})

    // end event
    .on('end', function() {

      // Calling bytesWritten property
      console.log(zlibs.bytesWritten);

    })
   .end(buffer);
});
```

**输出:**

```
16
```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ bytes step](https://nodejs.org/api/zlib.html#zlib_zlib_byteswritten)