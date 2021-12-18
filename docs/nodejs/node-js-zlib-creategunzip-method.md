# Node.js zlib.createGunzip()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-creategunzip-method/](https://www.geeksforgeeks.org/node-js-zlib-creategunzip-method/)

**zlib.createGunzip()方法**是 zlib 模块的内置应用程序编程接口，用于创建新的 Gunzip 对象。

**语法:**

```
zlib.createGunzip( options )
```

**参数:**该方法接受单参数**选项**，这是一个保存 zlib 选项的可选参数。

**返回值:**返回一个新的 Gunzip 对象。

下面的例子说明了在 Node.js 中使用 **zlib.createGunzip()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// createGunzip() method

// Including zlib module
var zlib = require('zlib');

// Calling gzip function to compress data
zlib.gzip('GeeksforGeeks', function(err, data) {
  if (err) { 
    return console.log('err', err);
  }

  // Calling createGunzip method
  // to decompress the data again
  var gunzip = zlib.createGunzip();
  gunzip.write(data);
  gunzip.on('data', function (data)
   {
      console.log(data.toString());
  });
});
```

**输出:**

```
GeeksforGeeks

```

**例 2:**

```
// Node.js program to demonstrate the     
// createGunzip() method

// Including zlib module
var zlib = require('zlib');

// Calling gzip function to compress data
zlib.gzip('GfG', function(err, data) {
  if (err) { 
    return console.log('err', err);
  }

  // Calling createGunzip method
  // to decompress the data again
  var gunzip = zlib.createGunzip();
  gunzip.write(data);
  gunzip.on('data', function (data)
   {
      // Encoding the data
      console.log(data.toString('hex'));
  });
});
```

**输出:**

```
476647

```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ create gunzip _ options](https://nodejs.org/api/zlib.html#zlib_zlib_creategunzip_options)