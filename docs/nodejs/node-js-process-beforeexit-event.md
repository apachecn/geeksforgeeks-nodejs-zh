# 退出事件前的 Node.js 流程

> 原文:[https://www . geesforgeks . org/node-js-process-before exit-event/](https://www.geeksforgeeks.org/node-js-process-beforeexit-event/)

**“before exit”**是流程模块中流程类的一个事件，当 Node.js 清空其事件循环并且没有额外的工作要调度时发出。

**语法:**

```js
Event: 'beforeExit'
```

**参数**:此事件不接受任何参数作为参数。

**返回值:**此事件只返回一个回调函数，以便进一步操作。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Process 'beforeExit' Event

// Importing process module
const process = require('process');

// Event 'beforeExit'
process.on('beforeExit', (code) => {
   console.log('Process beforeExit event with code: ', code);
});

// Event 'exit'
process.on('exit', (code) => {
   console.log('Process exit event with code: ', code);
});

// Display the first message 
console.log('This message is displayed first.');
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
This message is displayed first.
Process beforeExit event with code:  0
Process exit event with code:  0
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Process 'beforeExit' Event

// Importing process module
const process = require('process');

// Updating the exit code
process.exitCode = 100;

// Event 'beforeExit'
process.on('beforeExit', (code) => {
   console.log('Process beforeExit event with code: ', code);
});

// Display the first message 
console.log('This message is displayed first.');
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
This message is displayed first.
Process beforeExit event with code:  100
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ event _ before exit](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_event_beforeexit)