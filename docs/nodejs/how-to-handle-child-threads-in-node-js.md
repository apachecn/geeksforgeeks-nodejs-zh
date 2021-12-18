# 如何处理 Node.js 中的子线程？

> 原文:[https://www . geesforgeks . org/如何处理节点中的子线程-js/](https://www.geeksforgeeks.org/how-to-handle-child-threads-in-node-js/)

Node.js 是一种单线程语言，在 I/O 调用时，在后台使用多线程来执行某些任务，但它不向开发人员公开子线程。
但是 node.js 为我们提供了一些方法，如果我们真的需要与我们的主单线程进程并行进行一些工作的话。
**节点中的子进程:**子进程模块通过访问操作系统命令，赋予节点运行子进程的能力。
**示例:** **文件名:parallelProcess.js**

## java 描述语言

```
// Do any work in parallel to main
// event loop or main process
console.log('Child Process Starts')
setTimeout(() => {
    console.log('Data processed')
}, 5000)
```

**文件名:main . js**T2】

## java 描述语言

```
const { fork } = require('child_process');

// Fork another process
const child_process = fork('./parallelProcess.js');

// Data we may need to send to the child process
const data = {}

console.log('Before process')

// Send the data to forked process
child_process.send({ data }, function(){
    console.log('Sending data')
});

// Listen to forked process
child_process.on('close', (result) => {
    console.log('Child process terminated and returned');
});

console.log('After process')
```

**输出:**

```
Before process
After process
Child Process Starts
Data processed
Child process terminated and returned
```

**工作线程**Worker _ Threads 模块支持使用并行执行 JavaScript 的线程。工作线程对于执行 CPU 密集型的 JavaScript 操作非常有用。它们对输入/输出密集型工作没有多大帮助，而使用 Node.js 内置的异步输入/输出操作可以更好地完成这些工作。
**例:**

## java 描述语言

```
const {Worker, isMainThread, parentPort}
            = require('worker_threads');

if (isMainThread) {

    // Main code, only executed for main thread
    const worker = new Worker(__filename, {
        workerData: {}
    });

    worker.on('message', (m) => console.log(
                  'Thread send message:', m));

    worker.on('error', () => console.log('Error'));
    worker.on('exit', () => {
        console.log('Worker exit')
    });
} else {

    // Worker thread code, only execute
    // for working thread.
    setTimeout(() => {
        parentPort.postMessage('Hello World!');
    }, 3000)
}
```

**输出:**

```
Thread send message: Hello World!
Worker exit
```

进程有自己的内存空间另一方面，线程使用共享的内存空间。线程是过程的一部分。由于 worker_threads 在同一个进程中创建新线程，因此需要的资源更少。
**参考:**
[https://nodejs.org/api/child_process.html](https://nodejs.org/api/child_process.html)
https://nodejs.org/api/worker_threads.html