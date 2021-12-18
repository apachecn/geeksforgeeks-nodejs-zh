# Node.js process.argv0 属性

> 原文:[https://www . geesforgeks . org/node-js-process-argv 0-property/](https://www.geeksforgeeks.org/node-js-process-argv0-property/)

**process.argv0 属性**是进程模块的内置应用编程接口，用于在运行命令行时获取传递给 node.js 进程的 argv[0]原始值的只读副本。

**语法:**

```
process.argv0
```

**返回值:**该属性返回一个字符串，指定在命令行中运行时传递给进程的第一个参数。

下面的例子说明了 **process.argv0 属性**在 Node.js 中的使用:

**示例:**

```
// Node.js program to demonstrate the
// process.argv0 Property

// Include process module
const process = require('process');

// Printing process.argv0 property value
console.log(process.argv0);
```

**输出:**

```
node.exe
```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_argv0