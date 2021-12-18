# Node.js Buffer.readIntBE()方法

> 原文:[https://www . geesforgeks . org/node-js-buffer-readint be-method/](https://www.geeksforgeeks.org/node-js-buffer-readintbe-method/)

**Buffer.readIntBE()方法**用于读取给定偏移量处的缓冲区字节数，并将结果解释为二进制补码有符号值。

**语法:**

```
buffer.readIntBE( offset, byteLen )
```

**参数:**该方法接受两个参数，如上所述，如下所述:**偏移量:**指定缓冲对象的位置。它表示开始读取前要跳过的字节数。偏移值位于范围 **0 到缓冲区长度–字节数**之间。
**字节数:**它是一个整数值，表示从给定偏移量读取的字节数。该参数值介于 **0 和 6** 之间。

**返回值:**从大端指定的偏移量开始返回一个字节数为**的整数**值。

**例 1:**

```
// Node.js program to demonstrate the
// buffer.readIntBE(offset, bytelen) method 
const buff = Buffer.from([0x11, 0x12, 0x34, 0x56, 0x89, 0xcd]);

console.log(buff.readIntBE(0, 5).toString(16));

console.log(buff.readIntBE(0, 4).toString(16));
```

**输出:**

```
1112345689
11123456

```

**例 2:**

```
// Node.js program to demonstrate the
// buffer.readIntBE(offset, bytelen) method 
const buff = Buffer.from([0x11, 0x12, 0x34, 0x56, 0x89, 0xcd]);

console.log(buff.readIntBE(4, 6).toString(16));

console.log(buff.readIntBE(3, 0).toString(16));
```

**输出:**

```
buffer.js:831
    throw new RangeError('Index out of range');
    ^

RangeError: Index out of range
    at checkOffset (buffer.js:831:11)
    at Buffer.readIntBE (buffer.js:938:5)
    at Object. (/home/cg/root/8545664/main.js:8:17)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)
    at Function.Module._load (module.js:438:3)
    at Module.runMain (module.js:604:10)
    at run (bootstrap_node.js:389:7)

```

上面的示例显示了错误，因为它的参数不在有效范围内。

**注:**

*   要获取小端格式的值，您可以使用 Buffer.readIntLE()方法。
*   以上程序将使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/buffer . html # buff _ readintbe _ offset _ byte length](https://nodejs.org/api/buffer.html#buffer_buf_readintbe_offset_bytelength)