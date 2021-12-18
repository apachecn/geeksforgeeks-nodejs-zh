# Node.js process.exitCode 属性

> 原文:[https://www . geesforgeks . org/node-js-process-exit code-property/](https://www.geeksforgeeks.org/node-js-process-exitcode-property/)

终止 Node.js 程序通常有两种方法，分别是使用 **process.exit()** 或 **process.exitCode** 变量。在这篇文章中，我们讨论了 process.exitCode 变量。它是一个整数，表示传递给 process.exit()函数的代码或进程自行退出时的代码。它允许 Node.js 程序自然退出，避免 Node 程序围绕事件循环调度做额外的工作，比传递 exitcode 给 process.exit()安全得多。

**语法**

```
  process.exitCode = value
```

这里的值是指 exitcode 值。

**示例 1** :一种方法是将 exitcode 值传递给 process.exit()函数。当未处理的未处理的致命异常发生时，使用退出代码 1，而当不再发生异步操作时，使用退出代码 0 终止。

## Javascript

```
const express = require('express')
const app = express()

var a=10;
var b=20;

if(a==10){
  console.log(a)
  process.exitCode(1);
}

console.log(b);

app.listen(3000, () => 
console.log('Server ready'))
```