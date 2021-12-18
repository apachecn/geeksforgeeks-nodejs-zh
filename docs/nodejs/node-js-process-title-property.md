# Node.js process.title 属性

> 原文:[https://www . geesforgeks . org/node-js-process-title-property/](https://www.geeksforgeeks.org/node-js-process-title-property/)

**流程标题属性**是流程模块的内置应用编程接口，用于获取和设置流程标题。

**语法:**

```js
process.title
```

**返回值:**该属性返回一个指定进程标题的字符串值，当前值为' ps '。

**注意:**为该属性赋予新值将修改当前值。不同的平台可以对进程标题的最大长度施加限制。

下面的例子说明了**流程标题属性**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// process.title property

// Include process module
const process = require('process');

// Printing process.title property value
console.log("PID: " + process.pid + 
      " process title is " + process.title);
```

**输出:**

```js
PID: 8852 process title is Command Prompt - node  title_1

```

**例 2:**

```js
// Node.js program to demonstrate the    
// process.title property

// Include process module
const process = require('process');

// Printing process.title property value
console.log("Before modification: PID: " + process.pid
          +" process title is " + process.title);

// Setting new process title value
process.title = "gekchosCustomProcess";

// Printing process.title value after modification
console.log("After modification: PID: " + process.pid
          + " process title is " + process.title);
```

**输出:**

```js
Before modification: PID: 14012 process title is Command Prompt - node  title_2
After modification: PID: 14012 process title is gekchosCustomProcess

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_title