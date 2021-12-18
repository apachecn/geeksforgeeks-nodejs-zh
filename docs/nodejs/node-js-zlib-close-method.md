# Node.js zlib.close()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-close-method/](https://www.geeksforgeeks.org/node-js-zlib-close-method/)

**zlib.close()方法**是 zlib 模块的内置应用编程接口，用于关闭底层句柄。

**语法:**

```
zlib.close( callback )
```

**参数:**该方法接受单参数**回调**，保存回调函数。

下面的例子说明了 **zlib.close()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// zlib.close() method

// Including zlib module
const zlib = require('zlib');

// Constructing createGzip and createGunzip
const input = zlib.createGzip();
const output = zlib.createGunzip();

// Piping
input.pipe(output);

// Write to stream
input.write('GeeksforGeeks');

// Calling flush method
input.flush();

// Calling close method
input.close();

// Check output
output.on('data', (d) => {
    console.log('Input: Data flush received '
                + d.length + ' bytes');
});
console.log("Closed!");
```

**输出:**

```
Closed!

```

**例 2:**

```
// Node.js program to demonstrate the     
// zlib.close() method

// Including zlib and fs module
const zlib = require("zlib");
const fs = require('fs');

// Creating readable Stream
const inp = fs.createReadStream('input.text');

// Creating writable stream
const out = fs.createWriteStream('input.txt.gz');

// Calling createDeflateRaw method
const defR = zlib.createDeflateRaw();

// Calling close method
defR.close();

// Piping
inp.pipe(defR).pipe(out);
console.log("Program Completed!");
```

**输出:**

```
Program Completed!

```

在这里，管道没有完成，因为关闭方法关闭了隐藏的句柄。

**参考:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ close _ callback](https://nodejs.org/api/zlib.html#zlib_zlib_close_callback)