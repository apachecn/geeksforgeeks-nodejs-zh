# Node.js Buffer.readInt32LE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readint 32 le-method/](https://www.geeksforgeeks.org/node-js-buffer-readint32le-method/)

**Buffer.readInt32LE()方法**用于从给定偏移量的缓冲区对象中读取 32 位整数，并以小端字节顺序返回结果。

**语法:**

```js
buffer.readInt32LE( offset )
```

**参数:**该方法接受单个参数**偏移**，指定缓冲对象的位置。它表示开始读取前要跳过的字节数。偏移值介于 **0 到 buff . length–4**之间。默认值为 0。

**返回值:**该方法在小端字节序中指定的偏移量处读取一个带符号的 32 位整数。

**例 1:**

```js
// Node.js program to demonstrate the
// buffer.readInt32LE() method 
const buff = Buffer.from([1, 2, 3, 4, 5]);

console.log(buff.readInt32LE(0));

console.log(buff.readInt32LE(1));
```

**输出:**

```js
67305985
84148994

```

**例 2:**

```js
// Node.js program to demonstrate the
// bufferobj.readInt32LE() method 
const buff = Buffer.from([1, 2, 3, 4, 5]);

console.log(buff.readInt32LE(4))
```

**输出:**

```js
buffer.js:831
    throw new RangeError('Index out of range');
    ^

RangeError: Index out of range
    at checkOffset (buffer.js:831:11)
    at Buffer.readInt32LE (buffer.js:984:5)
    at Object. (/home/cg/root/8545664/main.js:8:18)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)
    at Function.Module._load (module.js:438:3)
    at Module.runMain (module.js:604:10)
    at run (bootstrap_node.js:389:7)

```

上面的示例显示了错误，因为它的参数不在有效范围内。

**注意:**

*   To get the value in small format, you can use the **buffer.readint32be () method** .
*   The above programs are compiled and run with the `node index.js` command.

**参考:**T2【https://nodejs . org/API/buffer . html # buffer _ buf _ readint 32 le _ offset