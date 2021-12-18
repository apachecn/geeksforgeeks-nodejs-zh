# 节点. js 进程.报表.文件名属性

> 原文:[https://www . geesforgeks . org/node-js-process-report-filename-property/](https://www.geeksforgeeks.org/node-js-process-report-filename-property/)

**process.report.filename** 是流程模块内 process 类的内置应用编程接口，用于获取或设置编写报表的文件名。

**语法:**

```js
const process.report.filename
```

**参数**:这个 api 不接受任何参数作为参数。

**返回值**:这个 api 返回写报告的文件名。

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// Process.report.filename Property

// Importing process module
const process = require('process');

// Assigning the file name
process.report.filename = "GFG"

// Display the result
console.log(process.report.filename)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
GFG
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// Process.report.filename Property

// Importing process module
const process = require('process');

const filename = process.report.filename;

// Display the result
if (filename.length == 0)
    console.log("No file name is assigned")
else
    console.log(filename)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
No file name is assigned
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ process _ report _ filename](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_report_filename)