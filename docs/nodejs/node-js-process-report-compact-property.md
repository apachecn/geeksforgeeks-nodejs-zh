# 节点. js 流程.报表.紧凑属性

> 原文:[https://www . geesforgeks . org/node-js-process-report-compact-property/](https://www.geeksforgeeks.org/node-js-process-report-compact-property/)

**过程报告**是一个对象，其方法用于生成当前过程的诊断报告。 **process.report.compact** 以紧凑的格式编写报告，单行 JSON，比默认的多行格式更容易被日志处理系统使用。

**语法:**

```js
process.report.compact
```

**返回值:**该属性返回一个布尔值。

下面的例子说明了 Node.js 中 process.report.compact 属性的使用:

**示例:**

## index.js

```js
// Node.js program to demonstrate the 
// process.report.compact Property 

// Include process module 
const process = require('process'); 

// Printing process.report.compact property value 
console.log(`Reports are compact? ${process.report.compact}`);
```

**运行命令:**

```js
node index.js
```

**输出:**

![](img/9f3ea1c1b58a93953b3d53431f9e45af.png)

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ report _ compact](https://nodejs.org/api/process.html#process_process_report_compact)