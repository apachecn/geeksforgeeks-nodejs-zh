# Node.js process.execPath 属性

> 原文:[https://www . geesforgeks . org/node-js-process-exec path-property/](https://www.geeksforgeeks.org/node-js-process-execpath-property/)

**process.execArgv 属性**是进程模块的内置应用编程接口，用于获取启动 node.js 进程的 node.js 可执行文件的绝对路径名。

**语法:**

```js
process.execArgv
```

**返回值:**该属性返回一个字符串，表示启动 node.js 进程的 node.js 可执行文件的绝对路径。

下面的例子说明了**process . execute 属性**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// process.execPath property

// Include process module
const process = require('process');

// Printing process.execPath
console.log(process.execPath);
```

**输出:**

```js
C:\Program Files\nodejs\node.exe

```

**例 2:**

```js
// Node.js program to demonstrate the    
// process.execPath property

// Include process module
const process = require('process');

// Include path module
const path = require('path');

// Printing process.execPath
var execpath = process.execPath
console.log(execpath);

// Seperated directories and file
console.log(execpath.split(path.sep));
```

**输出:**

```js
C:\Program Files\nodejs\node.exe
[ 'C:', 'Program Files', 'nodejs', 'node.exe' ]

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ exec path](https://nodejs.org/api/process.html#process_process_execpath)