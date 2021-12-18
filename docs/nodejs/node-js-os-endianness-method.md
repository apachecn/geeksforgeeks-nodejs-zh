# Node.js os.endianness()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-endianness-method/](https://www.geeksforgeeks.org/node-js-os-endianness-method/)

字符顺序指的是一个数字的二进制表示中序列中的比特顺序。

**os.endianness()方法**是 os 模块的内置应用编程接口，用于获取为其编译 node.js 的计算机的 CPU 的 endianness。

**语法:**

```js
os.endianness()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个字符串值，指定 CPU 的字符顺序。返回的字符串将是`BE`(用于大端)或`LE`(用于小端)。

*   **LE:** 是序列中存储在较高内存地址的最高有效位/值。
*   **BE:** 是序列中最高有效位/值，存储在较低的内存地址中。

下面的例子说明了 **os.endianness()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// os.endianness() method

// Allocating os module
const os = require('os');

// Printing os.endianness() value
console.log(os.endianness());
```

**输出:**

```js
LE
```

**例 2:**

```js
// Node.js program to demonstrate the   
// os.endianness() method

// Allocating os module
const os = require('os');

// Printing os.endianness() value
switch(os.endianness()) {
    case 'LE':
      console.log("CPU is little endian format");
      break;

    case 'BE':
      console.log("CPU is big endian format");
      break;

    default:
      colsole.log("Unknown endianness");
}
```

**输出:**

```js
CPU is little endian format
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ endiance](https://nodejs.org/api/os.html#os_os_endianness)