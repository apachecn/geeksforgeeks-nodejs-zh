# Node.js 异步. queue()方法

> 原文:[https://www.geeksforgeeks.org/node-js-async-queue-method/](https://www.geeksforgeeks.org/node-js-async-queue-method/)

异步模块是为在 NodeJS 中使用**异步** JavaScript 而设计的。async.queue 返回一个**队列**对象，该对象能够**并发处理**，即一次处理多个项目。

**如何使用 async.queue？**

*   **步骤 1:** 创建 package.json 文件。通过运行以下命令创建一个 package.json 文件。

```js
npm init
```

*   **步骤 2:** 安装异步模块。可以使用以下命令安装异步模块。

```js
npm i async
```

*   **步骤 3:** 导入异步模块。可以使用以下命令导入异步模块。

```js
const async = require('async')
```

*   **步骤 4:** 使用异步队列模块。异步队列的语法。

```js
const queue = async.queue('function', 'concurrency value')
```

参数函数在添加到队列的元素上执行。**并发值**告诉队列在特定时间要处理的元素数量。

**示例:**请看下面的示例，以便更好地理解。

## java 描述语言

```js
// Defining The queue
const queue = async.queue((task, completed) => {
    // Here task is the current element being
    // processed and completed is the callback function

    console.log("Currently Busy Processing Task " + task);

    // Simulating a complex process.
    setTimeout(()=>{
        // Number of elements to be processed.
        const remaining = queue.length();
        completed(null, {task, remaining});
    }, 1000);

}, 1);

// The concurrency value is set to one,
// Which means that one element is being
// Processed at a particular time
```