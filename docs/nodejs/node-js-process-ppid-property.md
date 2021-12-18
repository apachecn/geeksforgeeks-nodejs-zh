# Node.js process.ppid 属性

> 原文:[https://www . geesforgeks . org/node-js-process-ppid-property/](https://www.geeksforgeeks.org/node-js-process-ppid-property/)

**process.ppid 属性**是流程模块的内置应用编程接口，用于获取当前父流程的 pid。

**语法:**

```
process.ppid
```

**返回值:**该属性返回一个整数值，指定当前父进程的 PID。

下面的例子说明了 **process.ppid 属性**在 Node.js 中的使用:

**示例:**

```
// Node.js program to demonstrate the
// process.ppid Property

// Include process module
const process = require('process');

// Printing process.pid value
console.log("process id is " + process.pid);

// Printing parent process.ppid
console.log("parent process id is " + process.ppid);
```

**输出:**

```
process id is 12024
parent process id is 12168

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_ppid