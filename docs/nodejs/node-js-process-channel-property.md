# 节点. js 流程.通道属性

> 原文:[https://www . geesforgeks . org/node-js-process-channel-property/](https://www.geeksforgeeks.org/node-js-process-channel-property/)

**进程通道**是进程模块内进程类的内置应用编程接口，用于获取对 IPC 通道的引用。如果不存在 IPC 通道，则该属性未定义。

**语法:**

```js
const process.channel
```

**参数**:这个 api 不接受任何参数作为参数。

**返回值:**该 api 返回对 IPC 通道的引用。如果不存在 IPC 通道，则该属性未定义。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Process.channel Property

// Importing process modules
const cp = require('child_process');

// Getting child process reference 
const process = cp.fork(`${__dirname}/sub.js`);

// Causes the child to print: 
// CHILD got message: { hello: 'world' }
process.send({ hello: 'world' });

console.log(process.channel)
```

## sub . js

```js
process.on('message', (m) => {
  console.log('CHILD got message:', m);

  process.exit()
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Control {
  _events: [Object: null prototype] {},
  _eventsCount: 0,
  _maxListeners: undefined,
  [Symbol(kCapture)]: false
}
CHILD got message: { hello: 'world' }
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Process.channel Property

// Importing process modules
const process = require('process');

// Getting process channel
if(process.channel) 
   console.log("Process Channel exist")
else
   console.log("Process Channel doesn't exist")
```

使用以下命令运行 **index.js** 文件:

**输出:**

```js
Process Channel doesn't exist
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ process _ channel](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_channel)