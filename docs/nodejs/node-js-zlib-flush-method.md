# Node.js zlib flush()方法

> 原文:[https://www.geeksforgeeks.org/node-js-zlib-flush-method/](https://www.geeksforgeeks.org/node-js-zlib-flush-method/)

对压缩流调用 **flush()方法**，这样它就可以迫使 **zlib** 返回当前可实现的最大输出。这种输出可能会以损坏压缩质量为代价返回，但当需要尽早访问数据时，这种输出可能会很有用。

**语法:**

```js
zlib.flush()
```

**参数:**此方法不接受任何参数。

**返回值:**目前尽可能多的返回数据。

下面的例子说明了 **zlib.flush()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// zlib.flush() method

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

// Check output
output.on('data', (d) => {
    console.log('Input: Data flush received ' 
    + d.length + ' bytes');
});
console.log("Program Complete!");
```

**输出:**

```js
Program Complete!
Input: Data flush received 13 bytes
```

**例 2:**

```js
// Node.js program to demonstrate the     
// zlib.flush() method

// Including zlib module
const zlib = require('zlib');

// Constructing createGzip and createGunzip
const input = zlib.createGzip();
const output = zlib.createGunzip();

// Piping
input.pipe(output);

// Writing to a stream of data 19000 bytes
input.write('G'.repeat(19000));

// Calling flush method with callback
input.flush(() => {});

// Check output
output.on('data', (d) => {
    console.log('Input: Data flush with callback received ' 
    + d.length + ' bytes');
});
console.log("Program Complete!");
```

**输出:**所以，当字节大小超过 16384 字节后，你需要回调 flush 方法，否则数据不会被完全刷新。

```js
Program Complete!
Input: Data flush with callback received 16384 bytes
Input: Data flush with callback received 2616 bytes

```

**参考资料:**[https://nodejs . org/API/zlib . html # zlib _ flushing](https://nodejs.org/api/zlib.html#zlib_flushing)