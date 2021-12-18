# Node.js zlib.createUnzip()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-create unzip-method/](https://www.geeksforgeeks.org/node-js-zlib-createunzip-method/)

**zlib.createUnzip()方法**是 zlib 模块的内置应用编程接口，用于创建新的 Unzip 对象。

**语法:**

```js
zlib.createUnzip( options )
```

**参数:**该方法接受单参数**选项**，这是一个保存 zlib 选项的可选参数。

**返回值:**返回一个新的解压对象。

下面的例子说明了在 Node.js 中使用 **zlib.createUnzip()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// createUnzip() method

// Including zlib module
var zlib = require('zlib');

// Calling gzip function to compress data
zlib.gzip('Nidhi Singh', function(err, data)
 {
  if (err) 
  { 
    return console.log('err', err);
  }

  // Calling createUnzip method
  // to decompress the data again
  var unzip = zlib.createUnzip();
  unzip.write(data);
  unzip.on('data', function (data)
   {
      console.log(data.toString());
  });
});
```

**输出:**

```js
Nidhi Singh

```

**例 2:**

```js
// Node.js program to demonstrate the     
// createUnzip() method

// Including zlib module
var zlib = require('zlib');

// Calling gzip function to compress data
zlib.gzip('Nidhi Singh', function(err, data)
 {
  if (err) 
  { 
    return console.log('err', err);
  }

  // Calling createUnzip method
  // to decompress the data again
  var unzip = zlib.createUnzip();
  unzip.write(data);
  unzip.on('data', function (data)
   {
      console.log(data.toString('hex'));
  });
});
```

**输出:**

```js
4e696468692053696e6768

```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ create unzip _ options](https://nodejs.org/api/zlib.html#zlib_zlib_createunzip_options)