# Node.js zlib.createGzip()方法

> 原文:[https://www . geesforgeks . org/node-js-zlib-creategzip-method/](https://www.geeksforgeeks.org/node-js-zlib-creategzip-method/)

**zlib.createGzip()方法**是 zlib 模块的内置应用编程接口，用于创建一个新的 Gzip 对象。

**语法:**

```js
zlib.createGzip( options )
```

**参数:**该方法接受单参数**选项**，这是保存 zlib 选项的可选参数。

**返回值:**返回一个新的 Gzip 对象。

以下示例说明了在 Node.js 中使用 **zlib.createGzip()方法**:

**例 1:**

```js
// Node.js program to demonstrate the     
// createGzip() method

// Including zlib and fs module
const zlib = require("zlib");
const fs = require('fs');

// Creating readable Stream
const inp = fs.createReadStream('input.txt');

// Creating writable stream
const out = fs.createWriteStream('input.txt.gz');

// Calling createGzip method
const gzip = zlib.createGzip();

// Piping
inp.pipe(gzip).pipe(out);
console.log("Gzip created!");
```

**输出:**

```js
Gzip created!

```

**例 2:**

```js
// Node.js program to demonstrate the     
// createGzip() method

// Including zlib and fs module
const zlib = require("zlib");
const fs = require('fs');

// Creating readable Stream
const inp = fs.createReadStream('input.txt');

// Creating writable stream
const out = fs.createWriteStream('input.txt.gz');

// Calling createGzip method
const gzip = zlib.createGzip();

// Piping
inp.pipe(out).pipe(gzip);
console.log("Gzip created!");
```

**输出:**

```js
Error [ERR_STREAM_CANNOT_PIPE]: Cannot pipe, not readable
    at WriteStream.Writable.pipe (_stream_writable.js:243:24)
    at /home/runner/SomberMonumentalCad/index.js:19:15
    at Script.runInContext (vm.js:133:20)
    at Object. (/run_dir/interp.js:156:20)
    at Module._compile (internal/modules/cjs/loader.js:778:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:789:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)

```

在这里，管道没有按照正确的顺序进行，因此会出现错误。

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ zlib _ create gzip _ options](https://nodejs.org/api/zlib.html#zlib_zlib_creategzip_options)