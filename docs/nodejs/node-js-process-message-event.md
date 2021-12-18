# Node.js 流程消息事件

> 原文:[https://www . geesforgeks . org/node-js-process-message-event/](https://www.geeksforgeeks.org/node-js-process-message-event/)

**“消息”**是进程模块中类进程的一个事件，每当子进程收到父进程使用 *childprocess.send()* 发送的消息时，就会发出该事件。

**语法:**

```
Event: 'message'
```

**参数:**此事件不接受任何参数作为参数。

**返回值:**此事件只返回一个回调函数，以便进一步操作。

**例 1:**

文件名是 index.js

## java 描述语言

```
// Node.js program to demonstrate the 
// Process 'message' Event

// Importing process module
const cp = require('child_process');

// Initiating child process
const process = cp.fork(`${__dirname}/sub.js`);

// Causes the child to print:
// CHILD got message: { hello: 'world' }
process.send({ hello: 'world' });
```

这里的文件名是 sub.js

## java 描述语言

```
// Importing process module
const process = require('process');

// Message Event
process.on('message', (m) => {
    console.log('CHILD got message:', m);
    process.exit(0)
});
```

使用以下命令运行**索引. js** 文件:

```
node index.js
```

**输出:**

```
CHILD got message: { hello: 'world' }
```

**例 2:**

文件名是 index.js

## java 描述语言

```
// Node.js program to demonstrate the 
// Process 'message' Event

// Importing process module
const cp = require('child_process');

// Initiating child process
const process = cp.fork(`${__dirname}/sub.js`);

// Message Event
process.on('message', (m) => {
    console.log('PARENT got message:', m);
});

// Causes the child to print:
// CHILD got message: { hello: 'world' }
process.send({ hello: 'world' });
```

这里的文件名是 sub.js

## java 描述语言

```
// Importing process module
const process = require('process');

// Message Event
process.on('message', (m) => {
    console.log('CHILD got message:', m);
    process.exit(0)
});

// Causes the parent to print:
// PARENT got message: { foo: 'bar', baz: null }
process.send({ foo: 'bar', baz: NaN });
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
CHILD got message: { hello: 'world' }
PARENT got message: { foo: 'bar', baz: null }
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ event _ message](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_event_message)