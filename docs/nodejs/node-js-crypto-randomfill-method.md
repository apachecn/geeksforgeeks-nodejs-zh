# Node.js crypto.randomFill()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-random fill-method/](https://www.geeksforgeeks.org/node-js-crypto-randomfill-method/)

**crypto.randomFill()方法**与 crypto.randomBytes()方法相同，但唯一的区别是这里的第一个参数是将被填充的`buffer`，它还有一个作为参数传递的回调函数。但是，如果回调函数不可用，则会引发错误。

**语法:**

```
crypto.randomFill( buffer, offset, size, callback )
```

**参数:**这个方法接受上面提到的和下面描述的四个参数:

*   **buffer:** This parameter holds data of buffer, TypedArray or DataView type.
*   **Offset:** is a number with a default value of 0.
*   **Size:** is a numerical value, and the default value is **(buffer. length–offset)** .
*   **Callback:** is a function with two parameters, namely err and buf.

**返回值:**返回缓冲。

下面的例子说明了 **crypto.randomFill()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the 
// crypto.randomFill() method

// Including crypto module
const crypto = require('crypto');

// Defining buffer
const buf = Buffer.alloc(6);

// Calling randomFill method with two
// of its parameters
crypto.randomFill(buf, (err, buf) => {

  if (err) throw err;

  // Prints random data in buffer
  console.log(buf.toString('ascii'));
});

// Calling randomFill method with all
// its parameters
crypto.randomFill(buf, 3, 2, (err, buf) => {

  if (err) throw err;

  // Prints random data in buffer
  console.log(buf.toString('base64'));
});

// The output of this is same as above
crypto.randomFill(buf, 3, 3, (err, buf) => {

  if (err) throw err;

  console.log(buf.toString('base64'));
});
```

**输出:**

```
&43Jho0s5v0
Jho0s5v0

```

这里，最后两个值是相同的。

**例 2:**

```
// Node.js program to demonstrate the 
// crypto.randomFill() method

// Including crypto module
const crypto = require('crypto');

// Defining dataview
const datv = new DataView(new ArrayBuffer(6));

// Calling randomFill method with DataView
// instance as buffer
crypto.randomFill(datv, (err, buf) => {

  if (err) throw err;

  // Prints random data which is encoded
  console.log(Buffer.from(buf.buffer, 
         buf.byteOffset, buf.byteLength)
    .toString('ascii'));
});
```

**输出:**

```
ceVMb

```

这里，任何*类型的 dArray 或 DataView* 实例都作为缓冲区传递，在每次运行中，您将获得不同的输出。

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ randomill _ buffer _ offset _ size _ callback](https://nodejs.org/api/crypto.html#crypto_crypto_randomfill_buffer_offset_size_callback)