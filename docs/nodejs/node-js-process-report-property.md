# 节点. js 流程.报表属性

> 原文:[https://www . geesforgeks . org/node-js-process-report-property/](https://www.geeksforgeeks.org/node-js-process-report-property/)

**process.report** 是流程模块内 process 类的内置应用编程接口，用于提供生成当前流程诊断报告的方法。

**语法:**

```
const process.report
```

**返回值:**该属性返回生成当前流程诊断报告的方法。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Process.report Property

// Importing process module
const process = require('process');

// Getting reports of the current process
const reports = process.report;

// Display the result
console.log(reports)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
{
  writeReport: [Function: writeReport],
  getReport: [Function: getReport],    
  directory: [Getter/Setter],
  filename: [Getter/Setter],
  compact: [Getter/Setter],
  signal: [Getter/Setter],
  reportOnFatalError: [Getter/Setter],
  reportOnSignal: [Getter/Setter],
  reportOnUncaughtException: [Getter/Setter]
}
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// Process.report Property

// Importing process module
const process = require('process');

// If Report is present
if (process.report) {
   // Printing Report Compact Status
   console.log(process.report.compact)
} else {
   console.log("Unable to print Report Compact Status")
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
false
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ process _ report](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_report)