# Node.js process.stderr 属性

> 原文:[https://www . geesforgeks . org/node-js-process-stderr-property/](https://www.geeksforgeeks.org/node-js-process-stderr-property/)

**process.stderr** 是流程模块中 process 类的内置应用编程接口，用于返回连接到 stderr 的流。

**语法:**

```
const process.stderr
```

**参数**:这个 api 不接受任何参数作为参数。

**返回值**:这个 api 返回一个连接到 stderr 的流。

**例 1:**

**文件名:index . js**

## 【JavaScript】

```
// Node.js program to demonstrate the 
// Process.stderr

// Importing process module
const process = require('process');

// Getting the stream
// by using process.stderr
const stream = process.stderr

// Display the result
console.log(stream.rows)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
16
```

**例 2:**

**文件名:index . js**

## 【JavaScript】

```
// Node.js program to demonstrate the 
// Process.stderr

// Importing process module
const process = require('process');

// Display the result
console.log(process.stderr.columns)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
147
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ process _ stderr](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_stderr)