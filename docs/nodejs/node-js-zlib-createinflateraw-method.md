# node . js zlib . createBulgeraw()方法

> 原文:[https://www . geeksforgeeks . org/node-js-zlib-createdugeraw-method/](https://www.geeksforgeeks.org/node-js-zlib-createinflateraw-method/)

方法是 zlib 模块的内置应用编程接口，用于创建一个新的充气对象。

**语法:**

```js
zlib.createInflateRaw( options )
```

**参数:**该方法接受单参数**选项**，这是一个保存 zlib 选项的可选参数。

**返回值:**返回一个新的充气对象。

下面的例子说明了在 Node.js 中使用**方法:**

**例 1:**

```js
// Node.js program to demonstrate the     
// createInflateRaw() method

// Including zlib module
var zlib = require('zlib');

// Calling deflateRaw function to compress data
zlib.deflateRaw('Decompressed..', function(err, data)
 {
  if (err) 
  { 
    return console.log('err', err);
  }

  // Calling createInflateRaw method
  // to decompress the data again
  var gunzip = zlib.createInflateRaw();
  gunzip.write(data);
  gunzip.on('data', function (data)
   {
      console.log(data.toString());
  });
});
```

**输出:**

```js
Decompressed..

```

**例 2:**

```js
// Node.js program to demonstrate the     
// createInflateRaw() method

// Including zlib module
var zlib = require('zlib');

// Calling deflateRaw function to compress data
zlib.deflateRaw('Decompressed..', function(err, data)
 {
  if (err) 
  { 
    return console.log('err', err);
  }

  // Calling createInflateRaw method
  // to decompress the data again
  var gunzip = zlib.createInflateRaw();
  gunzip.write(data);
  gunzip.on('data', function (data)
   {
      console.log(data.toString('base64'));
  });
});
```

**输出:**

```js
RGVjb21wcmVzc2VkLi4=

```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ create inflate _ options](https://nodejs.org/api/zlib.html#zlib_zlib_createinflateraw_options)