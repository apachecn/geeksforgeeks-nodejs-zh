# Node.js Worker.isMainThread 属性

> 原文:[https://www . geesforgeks . org/node-js-worker-ismainthread-property/](https://www.geeksforgeeks.org/node-js-worker-ismainthread-property/)

worker_threads 模块中 Worker 类的内置应用程序编程接口**Worker . IsInthread**属性用于检查当前线程是否在 Worker 线程中运行。

**语法:**

```js
const Worker.isMainThread
```

**参数:**该属性不接受任何参数。

**返回值:**如果当前线程不在工作线程内运行，则该属性返回布尔值 true，否则返回 false。

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate 
// the Worker.isMainThread  API

// Importing worker_thread module
const { Worker, isMainThread } = require('worker_threads');

// Checking if the current thread is inside the
// Main thread or not by using IsMainThread API
if (isMainThread) {
  console.log('OutSide Worker!2');
  console.log('1');
  console.log('2');
  console.log('3');
  console.log(isMainThread); 
}
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
OutSide Worker!2
1
2
3
true

```

**示例 2:** **文件名:**

```js
// Node.js program to demonstrate the
// Worker.isMainThread  API

// Importing worker_thread module
const { Worker, isMainThread } 
    = require('worker_threads');

// Checking if the current thread is 
// inside the main thread or not
// by using IsMainThread API
if (isMainThread) {

   // This re-loads the current file
   // inside a Worker instance.
   new Worker(__filename);
} else {
  console.log('Inside Worker!2');
  console.log('1');
  console.log('2');
  console.log('3');
  console.log(isMainThread); 
}
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Inside Worker!2
1
2
3
false

```

**参考:**T2】https://nodejs . org/dist/latest-v 12 . x/docs/API/worker _ threads . html # worker _ threads _ worker _ ismainthread