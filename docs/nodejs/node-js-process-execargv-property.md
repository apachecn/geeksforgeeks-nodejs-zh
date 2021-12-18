# Node.js process.execArgv 属性

> 原文:[https://www . geesforgeks . org/node-js-process-execargv-property/](https://www.geeksforgeeks.org/node-js-process-execargv-property/)

**process.execArgv 属性**是流程模块的内置应用编程接口，用于在启动过程中获取传递给 node.js 流程的 node.js 特定命令行选项。

**语法:**

```js
process.execArgv
```

**返回值:**该属性返回一个数组字符串，该字符串包含 node.js 进程启动期间传递的 node.js 特定命令行选项。它不包括 node.js 应用程序的路径或 js 文件的路径。用父进程的执行环境来生成子进程是很有用的。

下面的例子说明了 **process.execArgv 属性**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the
// process.execArgv Property

// Include process module
const process = require('process');

// Printing process.execArgv property value
console.log(process.execArgv);
```

**命令运行:**

```js
node -i --harmony filename
```

**输出:**

```js
[ '-i', '--harmony' ]

```

**例 2:**

```js
// Node.js program to demonstrate the
// process.execArgv Property

// Include process module
const process = require('process');

// Printing process.execArgv property value
var execargv = process.execArgv;
console.log("number of execution arguments is "
        + execargv.length);

execargv.forEach((val, index) => {
    console.log(`${index}: ${val}`);
});
```

**命令运行:**

```js
node -i --harmony filename

```

**输出:**

```js
number of execution arguments is 2
0: -i
1: --harmony

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ execargv](https://nodejs.org/api/process.html#process_process_execargv)