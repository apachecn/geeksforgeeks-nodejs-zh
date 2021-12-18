# node . js buffer . read trell()方法

> 原文:[https://www . geeksforgeeks . org/node-js-buffer-readi trell-method/](https://www.geeksforgeeks.org/node-js-buffer-readintle-method/)

**Buffer . ReadyLel()方法**用于从给定偏移量的缓冲区中读取字节数，并将结果解释为二进制补码有符号值。

**语法:**

```
buffer.readIntLE( offset, byteLen )
```

**参数:**该方法接受两个参数，如上所述，如下所述:
**偏移量:**指定缓冲对象的位置。它表示开始读取前要跳过的字节数。它位于 **0 到缓冲区的范围内。长度–字节**。
**字节数:**它是一个整数值，表示从给定偏移量读取的字节数。该参数值位于 **0 和 6** 之间。

**返回值:**它返回一个**整数**值，字节数从指定的偏移量开始以小端字节为单位。

**例 1:**

```
// Node.js program to demonstrate the
// buffer.readIntLE( offset, byteLen ) method 
const buff = Buffer.from([0x11, 0x12, 0x34, 0x56, 0x89, 0xcd]);

console.log(buff.readIntLE(0, 5).toString(16));

console.log(buff.readIntLE(0, 4).toString(16));
```

**输出:**

```
-76a9cbedef
56341211

```

**例 2:**

```
// Node program to demonstrate the
// buffer.readIntLE( offset, bytelen ) method 
const buff = Buffer.from([0x11, 0x12, 0x34, 0x56, 0x89, 0xcd]);

console.log(buff.readIntLE(4, 6).toString(16));

console.log(buff.readIntLE(3, 0).toString(16));
```

**输出:**

```
buffer.js:831
    throw new RangeError('Index out of range');
    ^

RangeError: Index out of range
    at checkOffset (buffer.js:831:11)
    at Buffer.readIntLE (buffer.js:918:5)
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

*   要获取大端格式的值，可以使用 Buffer.readIntBE()方法。
*   以上程序将使用`node index.js`命令编译运行。