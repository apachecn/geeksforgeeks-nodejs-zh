# node . js process . report . write report()方法

> 原文:[https://www . geesforgeks . org/node-js-process-report-write report-method/](https://www.geeksforgeeks.org/node-js-process-report-writereport-method/)

**process . report . write report()**方法将诊断报告写入文件。如果未提供文件名，默认文件名包括日期、时间、PID 和序列号。报告的 JavaScript 堆栈跟踪取自 err(如果有)。

**语法:**

```
process.report.writeReport([filename][, err])
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **文件名:**此参数保存将写入报告的文件名。
*   **err:** 此参数用于报告 javascript 堆栈。

**返回值:**该方法返回生成报告的文件名。

下面的例子说明了 Node.js 中 process.report.writeReport 属性的使用:

**示例:**

## java 描述语言

```
// Node.js program to demonstrate the 
// process.report.writeReport Property 

// Include process module 
import process from 'process'

// Printing process.report.writeReport property value 
process.report.writeReport();
```

**运行命令:**

```
node filename
```

**输出:**

![](img/37dbdd0d9873428fd35f5b1b768d0570.png)

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ report _ reportonsignal](https://nodejs.org/api/process.html#process_process_report_reportonsignal)