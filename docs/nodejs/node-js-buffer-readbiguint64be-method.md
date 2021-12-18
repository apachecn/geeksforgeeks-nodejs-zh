# node . js buffer . readbiguint64be()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readbiguint 64 be-method/](https://www.geeksforgeeks.org/node-js-buffer-readbiguint64be-method/)

**Buffer.readBigUInt64BE()方法**用于从给定偏移量的缓冲区对象中读取无符号 64 位整数，并以大端字节顺序返回结果。

**语法:**

```js
buffer.readBigInt64BE( offset )
```

**参数:**该方法接受单个参数**偏移**，指定缓冲对象的位置。它表示开始读取前要跳过的字节数。偏移值在 **0 到缓冲区长度–8**的范围内。默认值为 0。

**返回值:**该方法读取大端指定偏移量处的无符号 64 位**整数**。

**示例 1:**
**文件名:index.js**

```js
// Node.js program to demonstrate the
// buffer.readBigUInt64BE() method 
const buff = Buffer.from([0x00, 0x00, 
    0x0e, 0x00, 0xff, 0xff, 0xff, 0xff]);

// Getting big interer value by
// using readBigUInt64BE method
const value = buff.readBigUInt64BE(0);

// Display the result
console.log("Big Integer :- " + value);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Big Integer :- 15397457756159

```

**示例 2:**
**文件名:index.js**

```js
// Node.js program to demonstrate the
// buffer.readBigUInt64BE() method 
const buff = Buffer.from([0x00, 0x00, 0x0e, 0x00, 0xff, 0xff, 0xff, 0xff]);

// Getting big integer value by
// using readBigUInt64BE method
const value = buff.readBigUInt64BE(1);

// Display the result
console.log("Big Integer :- " + value);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
internal/buffer.js:77
  throw new ERR_OUT_OF_RANGE(type || 'offset',
  ^

RangeError [ERR_OUT_OF_RANGE]: The value of "offset" is out of range. It must be >= 0 and
<= 0\. Received 1
    at boundsError (internal/buffer.js:77:9)
    at Buffer.readBigUInt64BE (internal/buffer.js:108:5)
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

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/buffer . html # buffer _ buf _ readbiguint64 be _ offset](https://nodejs.org/dist/latest-v12.x/docs/api/buffer.html#buffer_buf_readbiguint64be_offset)