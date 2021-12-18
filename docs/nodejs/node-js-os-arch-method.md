# node . js . OS . arch()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-arch-method/](https://www.geeksforgeeks.org/node-js-os-arch-method/)

**os.arch()方法**是 os 模块的内置应用编程接口，用于获取当前 node.js 所编译的计算机的 CPU 架构。

**语法:**

```
os.arch()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回当前 node.js 编译所针对的操作系统 CPU 架构。可能的值为“x32”、“x64”、“arm”、“arm64”、“s390”、“s390x”、“mipsel”、“ia32”、“mips”、“ppc”和“ppc64”。

下面的例子说明了 **os.arch()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// os.arch() method

// Allocating os module
const os = require('os');

// Printing os.arch()
console.log(os.arch());
```

**输出:**

```
x64
```

**例 2:**

```
<script>
// Node.js program to demonstrate the   
// os.arch() method

// Allocating os module
const os = require('os');

// Printing os.arch() description
// of the architecture
switch(os.arch()){
    case 'x32':
        console.log("32-bit extended system");
        break;

    case 'x64':
        console.log("64-bit extended system");
        break;

    case 'arm':
        console.log("32-bit  Advanced RISC Machine");
        break;

    case 'arm64':
        console.log("64-bit  Advanced RISC Machine");
        break;

    case 's390':
        console.log("31-bit The IBM System/390, the"
                + " third generation of the System/360"
                + " instruction set architecture");
        break;

    case 's390x':
        console.log("64-bit The IBM System/390, the"
                + " third generation of the System/360"
                + " instruction set architecture");
        break;

    case 'mipsel':
        console.log("64-bit Microprocessor without"
                + " Interlocked Pipelined Stages");
        break;

    case 'mips':
        console.log("32-bit Microprocessor without"
                + " Interlocked Pipelined Stages");
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
        console.log(" unknown processor");
}
</script>
```

**输出:**

```
64-bit extended system

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ arch](https://nodejs.org/api/os.html#os_os_arch)