# node . js process . report . reportoncatalerror 属性

> 原文:[https://www . geesforgeks . org/node-js-process-report-reportoncatalerror-property/](https://www.geeksforgeeks.org/node-js-process-report-reportonfatalerror-property/)

**进程**对象是一个全局对象，它提供关于当前 Node.js 进程的信息和控制。作为一个全局变量，它始终对 Node.js 应用程序可用，而无需使用 require()。也可以使用 require()显式访问，如下所示:

```
const process = require('process');
```

如果**process . report . reportoncatalerror**为真，则针对致命错误(如内存不足错误或失败的 C++断言)生成诊断报告。

**语法:**

```
process.report.reportOnFatalError
```

**参数:**该属性不接受任何参数。

**返回值:**该属性返回一个布尔值。

下面的例子说明了在 Node.js 中*进程的使用。*

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// process.report.reportOnFatalError  

// Include process module  
const process = require('process');  

// Printing process.report.reportOnFatalError
// property value  
console.log(`Report on fatal error: 
    ${process.report.reportOnFatalError}`);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Report on fatal error: false
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// process.report.reportOnFatalError  

// Include process module  
const process = require('process');  

process.report.reportOnFatalError = true;

// Printing process.report.reportOnFatalError
// property value  
console.log(`Report on fatal error: 
    ${process.report.reportOnFatalError}`);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Report on fatal error: true
```

**参考:**[https://nodejs . org/API/process . html # process _ process _ report _ reportoncatalerror](https://nodejs.org/api/process.html#process_process_report_reportonfatalerror)