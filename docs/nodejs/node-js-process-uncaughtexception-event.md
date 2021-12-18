# Node.js 进程未跳空异常事件

> 原文:[https://www . geeksforgeeks . org/node-js-process-uncut exception-event/](https://www.geeksforgeeks.org/node-js-process-uncaughtexception-event/)

**“未捕获异常”**是进程模块中进程类的一个事件，当一个未捕获的 JavaScript 异常一路冒泡回到事件循环时发出。

**语法:**

```
Event: 'uncaughtException'
```

**参数:**此事件不接受任何参数作为参数。

**返回值:**此事件只返回一个回调函数，以便进一步操作。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Process 'uncaughtException' Event

// Importing the modules
const process = require('process');
var fs = require('fs');

// Independent Block which will execute
setTimeout(() => {
   console.log('\n')
   console.log('Greetings from GeeksforGeeks');
}, 1000);

// Event 'uncaughtException'
process.on('uncaughtException', (error, source) => {
   fs.writeSync(process.stderr.fd, error, source);
});

// Throwing an exception
nonexistentFunc();

console.log('This Block of code will not run');
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
ReferenceError: nonexistentFunc is not defined

Greetings from GeeksforGeeks
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// Process 'uncaughtException' Event

// Importing the modules
const process = require('process');
var fs = require('fs');

// Event 'uncaughtException'
process.on('uncaughtException', (error) => {
   fs.writeSync(process.stderr.fd, error);
});

// Throwing our Error
throw new Error('Ran out of coffee')
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Error: Ran out of coffee
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ event _ uncut exception](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_event_uncaughtexception)