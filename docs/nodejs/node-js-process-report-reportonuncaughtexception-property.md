# node . js process . report . reportonancialistenexception 属性

> 原文:[https://www . geeksforgeeks . org/node-js-process-report-reportonuncalishexception-property/](https://www.geeksforgeeks.org/node-js-process-report-reportonuncaughtexception-property/)

**进程**对象是一个全局对象，它提供关于当前 Node.js 进程的信息和控制。作为一个全局变量，它始终对 Node.js 应用程序可用，而无需使用 require()。也可以使用 require()显式访问，如下所示:

```js
const process = require('process');
```

如果**process . report . reportunancialishexception**为真，则针对未捕获的异常生成诊断报告。

**语法:**

```js
process.report.reportOnUncaughtException
```

**参数:**该属性不接受任何参数。

**返回值:**该属性返回一个布尔值。

下面的例子说明了在 Node.js 中*进程的使用。*

**例 1:**

## index . js

```js
// Node.js program to demonstrate the  
// process.report.reportOnUncaughtException Property  

// Include process module  
const process = require('process');  

// Printing process.report.reportOnUncaughtException property value  
console.log(`Report on exception: 
   ${process.report.reportOnUncaughtException}`);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Report on exception: false
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the  
// process.report.reportOnUncaughtException Property  

// Include process module  
const process = require('process');  

process.report.reportOnUncaughtException = true;

// Printing process.report.reportOnUncaughtException property value  
console.log(`Report on exception: 
   ${process.report.reportOnUncaughtException}`);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Report on exception: true
```

**参考:**[https://nodejs . org/API/process . html # process _ process _ report _ reportonuncatouchexception](https://nodejs.org/api/process.html#process_process_report_reportonuncaughtexception)