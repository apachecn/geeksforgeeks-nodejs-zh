# 什么是 Node.js 中的链接？

> 原文:[https://www.geeksforgeeks.org/what-is-chaining-in-node-js/](https://www.geeksforgeeks.org/what-is-chaining-in-node-js/)

Node.js 中的链接可以使用异步 npm 模块来实现。为了安装异步模块，我们需要在目录中运行以下脚本:

```
npm init
npm i async
```

异步模块提供的链接功能有两种最常用的方法:

*   **并行(任务，回调):**任务是通过 I/O 切换在实践中并行运行的函数的集合。如果集合任务中的任何函数返回错误，将触发回调函数。一旦所有的函数都完成了，数据就会以数组的形式传递给回调函数。回调函数是可选的。
*   **系列(任务、回调)**:任务中的每个功能只有在前一个功能完成后才会运行。如果任何函数抛出错误，后续函数将不会执行，回调将使用错误值触发。任务完成后，数据作为数组传递给回调函数。

**示例 1:并行链接**
**文件名:index.js**

```
const async = require('async');

async.parallel([
    (callback) => {
        setTimeout(() => {
            console.log('This is the first function');
            callback(null, 1);
        }, 500);
    },
    (callback) => {
        console.log('This is the second function');
        callback(null, 2);
    }
], (err, results) => {
    if (err) console.error(err);
    console.log(results);
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
This is the second function
This is the first function
[ 1, 2 ]

```

**说明:**注意两个函数是异步执行的。因此，由于 setTimeout()方法，第二个函数的输出是在第一个函数完成执行之前收到的。但是，只有当两个函数都完成执行时，数据才会传递给回调。

**示例 2:系列链接**
**文件名:index.js**

```
const async = require('async');

async.series([
    (callback) => {
        setTimeout(() => {
            console.log('This is the first function');
            callback(null, 1);
        }, 500);
    },
    (callback) => {
        console.log('This is the second function');
        callback(null, 2);
    }
], (err, results) => {
    if (err) console.error(err);
    console.log(results);
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
This is the first function
This is the second function
[ 1, 2 ]

```

**解释:**与并行执行不同，在这种情况下，第二个函数直到第一个函数完成自己的执行后才执行。与并行方法类似，只有当 tasks 集合中的所有函数完成执行后，结果才会传递给回调函数。