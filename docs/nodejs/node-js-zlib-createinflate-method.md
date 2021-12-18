# node . js zlib . createBuild()方法

> 原文:[https://www . geeksforgeeks . org/node-js-zlib-create explain-method/](https://www.geeksforgeeks.org/node-js-zlib-createinflate-method/)

方法是 zlib 模块的内置应用编程接口，用于创建一个新的充气对象。

**语法:**

```
zlib.createInflate( options )
```

**参数:**该方法接受单参数**选项**，这是一个保存 zlib 选项的可选参数。

**返回值:**返回一个新的充气对象。

下面的例子说明了在 Node.js 中使用**zlib . createBuild()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// createInflate() method

// Including zlib module
var zlib = require('zlib');

// Calling deflate function to compress data
zlib.deflate('Hello World!', function(err, data)
 {
  if (err) 
  { 
    return console.log('err', err);
  }

  // Calling createInflate method
  // to decompress the data again
  var gunzip = zlib.createInflate();
  gunzip.write(data);
  gunzip.on('data', function (data)
   {
      console.log(data.toString());
  });
});
```

**输出:**

```
Hello World!

```

**例 2:**

```
// Node.js program to demonstrate the     
// createInflate() method

// Including zlib module
var zlib = require('zlib');

// Calling deflate function to compress data
zlib.deflate('Decompressed..', function(err, data)
 {
  if (err) 
  { 
    return console.log('err', err);
  }

  // Calling createInflate method
  // to decompress the data again
  var gunzip = zlib.createInflate();
  gunzip.write(data);
  gunzip.on('data', function (data)
   {
      console.log(data.toString('hex'));
  });
});
```

**输出:**

```
4465636f6d707265737365642e2e

```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ create inflate _ options](https://nodejs.org/api/zlib.html#zlib_zlib_createinflate_options)