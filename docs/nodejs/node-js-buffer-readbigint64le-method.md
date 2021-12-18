# node . js buffer . readbigint 64 le()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readbigint 64 le-method/](https://www.geeksforgeeks.org/node-js-buffer-readbigint64le-method/)

**Buffer.readBigInt64LE()方法**用于从给定偏移量的缓冲区对象中读取 64 位大整数，并以小端顺序返回结果。

**语法:**

```
buffer.readBigInt64LE( offset )
```

**参数:**该方法接受单个参数**偏移**，指定缓冲对象的位置。它表示开始读取前要跳过的字节数。偏移值在 **0 到缓冲区长度–8**的范围内。默认值为 0。

**返回值:**该方法读取小端指定偏移量处的有符号 64 位**大整数**。

**例 1:**

**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// buffer.readInt32LE() method
const buff = Buffer.from([0x00, 0x00,
    0x00, 0x00, 0xff, 0xff, 0xff, 0xff]);

// Getting big integer value by
// using readBigInt64LE method
const value = buff.readBigInt64LE(0);

// Display the result
console.log("Big Integer :- " + value);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Big Integer :- -4294967296
```

**例 2:**

**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// buffer.readInt32LE() method
const buff = Buffer.from([0x00, 0x00,
    0x00, 0x00, 0xff, 0xff, 0xff, 0xff]);

// Getting big integer value by
// using readBigInt64LE method
const value = buff.readBigInt64LE(1);

// Display the result
console.log("Big Integer :- " + value);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
internal/buffer.js:77
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range. It must be >= 0
 and <= 0\. Received 1
    at boundsError (internal/buffer.js:77:9)
    at Buffer.readBigInt64LE (internal/buffer.js:128:5)
    at Object. (F:\java\GFG.js:7:20)
    at Module._compile (internal/modules/cjs/loader.js:1138:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:1158:10)
    at Module.load (internal/modules/cjs/loader.js:986:32)
    at Function.Module._load (internal/modules/cjs/loader.js:879:14)
    at Function.executeUserEntryPoint [as runMain] (internal/modules/run_main.js:71:12)
    at internal/main/run_main_module.js:17:47 {
  code: 'ERR_OUT_OF_RANGE'
}
```

上面的示例显示了错误，因为它的参数不在有效范围内。
**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/buffer . html # buffer _ buf _ readbigint 64 le _ offset](https://nodejs.org/dist/latest-v12.x/docs/api/buffer.html#buffer_buf_readbigint64le_offset)