# 节点. js 流程.报表.报表信号属性

> 原文:[https://www . geesforgeks . org/node-js-process-report-reportonsignal-property/](https://www.geeksforgeeks.org/node-js-process-report-reportonsignal-property/)

**过程报告**是一个对象，其方法用于生成当前过程的诊断报告。如果**过程.报告.报告信号**为真，当过程接收到**过程.报告.信号**指定的信号时，将生成诊断报告。

**语法:**

```js
process.report.compact
```

**返回值:**该属性返回一个**布尔值**。

以下示例说明了 Node.js 中 process.report.reportOnSignal 属性的使用:

**示例:**

## index.js

```js
// Node.js program to demonstrate the 
// process.report.reportOnSignal Property 

// Include process module 
import process from 'process'

// Printing process.report.reportOnSignal property value 
console.log(`Report on signal: ${process.report.reportOnSignal}`);
```

**运行命令:**

```js
node index.js
```

**输出:**

![](img/0e808e93b8f80989b5514f07d8398261.png)

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ report _ reportonsignal](https://nodejs.org/api/process.html#process_process_report_reportonsignal)