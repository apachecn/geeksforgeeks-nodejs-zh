# node . js process . arch Property

> 原文:[https://www . geesforgeks . org/node-js-process-arch-property/](https://www.geeksforgeeks.org/node-js-process-arch-property/)

**process.arch 属性**是进程模块的内置应用编程接口，用于获取当前节点. js 所编译的计算机的 CPU 架构。

**语法:**

```js
process.arch
```

**返回值:**该属性返回为其编译当前 node.js 的操作系统 CPU 架构。可能的值为“x32”、“x64”、“arm”、“arm64”、“s390”、“s390x”、“mipsel”、“ia32”、“mips”、“ppc”和“ppc64”。

下面的例子说明了**进程的使用。**

**例 1:**

```js
// Node.js program to demonstrate the
// process.arch Property

// Include process module
const process = require('process');

// Printing process.arch property value
console.log(process.arch);
```

**输出:**

```js
x64
```

**例 2:**

```js
// Node.js program to demonstrate the
// process.arch Property

// Include process module
const process = require('process');

// Printing process.arch property value
switch(process.arch) {
    case 'x32':
        console.log("32-bit extended systems");
        break;
    case 'x64':
        console.log("64-bit extended systems");
        break;
    case 'arm':
        console.log("32-bit  Advanced RISC Machine");
        break;
    case 'arm64':
        console.log("64-bit  Advanced RISC Machine");
        break;
    case 's390':
        console.log("31-bit The IBM System/390, the "
                    + "third generation of the System/360"
                    + " instruction set architecture");
        break;
    case 's390x':
        console.log("64-bit The IBM System/390, the "
                    + "third generation of the System/360"
                    + " instruction set architecture");
        break;
    case 'mipsel':
        console.log("64-bit Microprocessor without "
                    + "Interlocked Pipelined Stages");
        break;
    case 'mips':
        console.log("32-bit Microprocessor without "
                    + "Interlocked Pipelined Stages");
        break;
    case 'ia32':
        console.log("32-bit Intel Architecture");
        break;
    case 'ppc':
        console.log("PowerPC Architecture.");
        break;
    case 'ppc64':
        console.log("64-bit PowerPC Architecture.");
        break;
    default:
        colsole.log(" unknown architecture");
}
```

**输出:**

```js
64-bit extended systems
```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_arch