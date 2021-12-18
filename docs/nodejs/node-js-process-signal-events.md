# 节点 js 过程信号事件

> 原文:[https://www . geesforgeks . org/node-js-process-signal-events/](https://www.geeksforgeeks.org/node-js-process-signal-events/)

信号是一个便携式操作系统接口互通系统。当节点接收到信号事件时，将会发出这些事件。为了通知事件已经发生，发送通知。

信号处理程序将接收信号的名称，并且信号名称基于每个事件的名称是大写的(例如，对于 SIGTERM 信号为“SIGTERM”)。

**语法:**

```
process.on(signalName, callback);
```

**参数:**该函数接受以下参数:

*   **Signal name:** is the signal name of the signal we want to call.
*   **Callback** : The callback function is executed.

**示例 1:** SIGINT 事件

通过终端在所有平台都支持，通常是用 **Ctrl+C** 生成的(也可以改)。启用终端原始模式并使用 Ctrl+C 时，不会生成。这里，文件名是

## Javascript

```
process.stdin.resume();

// If SIGINT process is called then this will
// run first then the next line
process.on('SIGINT', () => {
  console.log('Hey Boss I just Received SIGINT.');
});

// We are using this single function to handle multiple signals
function handle(signal) {
  console.log(`So the signal which I have Received is: ${signal}`);
}

process.on('SIGINT', handle);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**按下 ***ctrl + c*** 键，控制台屏幕上输出如下:

```
Hey Boss I just Received SIGINT.
So the signal which I have Received is: SIGINT
```

**示例 2:** SIGBREAK 事件

这里，文件名是

## Javascript

```
// Requiring module
const express = require('express')

const exp = express()

exp.get('/', (req, res) => {
 res.send('Hello Sir')
})

const server = exp.listen(3000, () => console.log('Server ready'))

// Is delivered on Windows when Ctrl+Break is pressed.
// On non-Windows platforms, it can be listened on, but there
// is no way to send or generate it.
process.on('SIGBREAK', () => {
 server.close(() => {
   console.log('SIGNAL BREAK RECEIVED')
 })
})
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**按下 ***ctrl +断开*** 生成信号键:

```
Server ready
SIGNAL BREAK RECEIVED
```

**注意:**你可以尝试 **SIGKILL** 信号，告诉一个进程立即关闭并作为*进程工作。您可以将此用作语法 *process.kill(process.pid，‘SIGTERM’)**

**SIGTERM:**SIGTERM 信号被发送到 Node.js 的一个进程，请求终止它。它不同于 SIGKILL 信号，可以被进程监听或忽略。这允许通过释放分配给它的资源，如数据库连接或文件句柄，很好地关闭进程。这种关闭应用程序的方式称为正常关闭。

**参考:**T2】https://nodejs.org/api/process.html#process_signal_events