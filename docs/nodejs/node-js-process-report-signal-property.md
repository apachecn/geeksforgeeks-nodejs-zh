# 节点. js 流程.报表.信号属性

> 原文:[https://www . geesforgeks . org/node-js-process-report-signal-property/](https://www.geeksforgeeks.org/node-js-process-report-signal-property/)

**过程报告**是一个对象，其方法用于生成当前过程的诊断报告。用于触发诊断报告创建的**信号**。默认为**‘sigusr 2’**。

**语法:**

```
process.report.signal
```

**返回值:**该属性返回当前流程生成的诊断报告。

下面的例子说明了 Node.js 中 process.report.signal 属性的使用:

**示例:**

## index.js

```
// Node.js program to demonstrate the 
// process.report.signal Property 

// Include process module 
const process = require('process'); 

// Printing process.report.signal property value 
console.log(`Report signal: ${process.report.signal}`);
```

**运行命令:**

```
node index.js
```

**输出:**

![](img/fcc7765ff0bd3e8e9a47f7f36fd3ba0d.png)

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ report _ signal](https://nodejs.org/api/process.html#process_process_report_signal)