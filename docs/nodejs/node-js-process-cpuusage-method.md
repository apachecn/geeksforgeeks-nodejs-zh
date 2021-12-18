# Node.js process.cpuUsage()方法

> 原文:[https://www . geesforgeks . org/node-js-process-cpuusage-method/](https://www.geeksforgeeks.org/node-js-process-cpuusage-method/)

**process.cpuUsage()方法**是 process 模块的内置应用编程接口，用于获取当前进程的用户、系统 CPU 时间使用情况。它作为具有属性 user 和 system 的对象返回，值以微秒为单位。返回值可能与实际运行时间不同，尤其是多核处理器。

**语法:**

```
process.cpuUsage( previous_value )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **previous_value:** 是可选参数，是调用 process.cpuUsage()之前返回的对象。如果通过，则返回差值。

**Return:** 这个方法在成功时返回一个对象，它包含像用户和系统这样的属性，带有一些整数值，表示进程经过的时间，以微秒为单位。

*   **用户:**表示用户经过的时间的整数
*   **系统:**是一个整数，表示系统经过的时间

下面的例子说明了 **process.cpuUsage()方法**在 Node.js 中的使用:

**例 1:**

## java 描述语言

```
// Allocating process module
const process = require('process');

// Calling process.cpuUsage() method
const usage = process.cpuUsage();

// Printing returned value
console.log(usage);
```

**输出:**

```
{ user: 78000, system: 15000 }
```

**例 2:**

## java 描述语言

```
// Allocating process module
const process = require('process');

// Calling process.cpuUsage() method
var usage = process.cpuUsage();
// Printing returned value
console.log("cpu usage before: ", usage);

// Current time
const now = Date.now();

// Loop to delay almost 100 milliseconds
while (Date.now() - now < 100);

// After using the cpu for nearly equal to 
// 100 milliseconds
// Calling process.cpuUsage() method
usage = process.cpuUsage(usage);

// Printing returned value
console.log("Cpu usage by this process: ", usage);
```

**输出:**

```
cpu usage before:  { user: 62000, system: 15000 }
Cpu usage by this process:  { user: 109000, system: 0 }
```

**参考:**[https://nodejs . org/API/process . html # process _ process _ cpuusage _ previous value](https://nodejs.org/api/process.html#process_process_cpuusage_previousvalue)T4】