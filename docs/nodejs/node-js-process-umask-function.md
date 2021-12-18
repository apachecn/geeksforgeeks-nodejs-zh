# Node.js process.umask()函数

> 原文:[https://www . geesforgeks . org/node-js-process-umask-function/](https://www.geeksforgeeks.org/node-js-process-umask-function/)

**进程**对象是一个全局对象，它提供关于当前 Node.js 进程的信息和控制。作为一个全局变量，它始终对 Node.js 应用程序可用，而无需使用 require()。也可以使用 require()函数显式访问它。

**process.umask(掩码)**设置 Node.js 进程的文件模式创建掩码。子进程从父进程继承掩码。返回上一个掩码。

**语法:**

```
process.umask()
```

**参数:**该方法将以下参数作为参数。

**返回值:**返回字符串或整数。

下面的例子说明了在 Node.js 中 process.umask(掩码)属性的使用:

**例:**

## js

```
// Node.js program to demonstrate the  
// process.umask(mask) Property  

// Include process module  
const process = require('process');  

const newmask = 0o022;
const oldmask = process.umask(newmask);

// Printing process.umask(mask) property value  
console.log(
  `Changed umask from ${oldmask.toString(8)} to ${newmask.toString(8)}`
);
```

**命令运行:**

```
node index.js
```

**输出:**

```
Changed umask from 2 to 22
```

**注意:**以上程序将使用 node index.js 命令编译运行。

**参考:**https://nodejs . org/API/process . html # process _ process _ umask _ mask