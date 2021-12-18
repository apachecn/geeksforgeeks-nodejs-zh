# Node.js 工作线程

> 原文:[https://www.geeksforgeeks.org/node-js-worker-threads/](https://www.geeksforgeeks.org/node-js-worker-threads/)

Node.js 中的**工作线程**对于执行繁重的 JavaScript 任务非常有用。在线程的帮助下，Worker 使并行运行 javascript 代码变得容易，从而使它变得更快、更高效。我们甚至可以在不干扰主线的情况下完成繁重的任务。旧版本的节点中没有引入工作线程。因此，首先更新你的 Node.js 来开始。

现在为实现这个线程创建两个文件，如下所示:
**文件名:worker.js**

```
const { workerData, parentPort } 
        = require('worker_threads')

console.log('Technical Articles on '
                    + workerData);

parentPort.postMessage(
    { fileName: workerData, status: 'Done' })
```

在这里，**工人数据**和**父端口**是工人线程的一部分。workerData 用于从线程中获取数据，parentPort 用于操作线程。 **postMessage()** 方法用于在控制台中发布给定的消息，方法是采用 workerData 获取的文件名。

**文件名:index.js**

```
const { Worker } = require('worker_threads')

function runService(workerData) {
    return new Promise((resolve, reject) => {
        const worker = new Worker(
                './worker.js', { workerData });
        worker.on('message', resolve);
        worker.on('error', reject);
        worker.on('exit', (code) => {
            if (code !== 0)
                reject(new Error(
`Stopped the Worker Thread with the exit code: ${code}`));
        })
    })
}

async function run() {
    const result = await runService('GeeksForGeeks')
    console.log(result);
}

run().catch(err => console.error(err))
```

这里，函数 **runService()** 返回一个 Promise 并运行工作线程。函数 **run()** 用于调用函数 **runService()** 并给出 **workerData** 的值。

**运行该应用程序的步骤:**运行以下命令:

```
node index.js
```

以下命令的输出如下所示:

```
Technical Articles on GeeksForGeeks
{ fileName: 'GeeksForGeeks', status: 'Done' }

```

**结论:**有了工作线程，我们可以实现更高效的应用程序，而不会造成死锁情况。这就是如何在应用程序中导入工作线程并实现该线程。