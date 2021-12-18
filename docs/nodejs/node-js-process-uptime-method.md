# Node.js process.uptime()方法

> 原文:[https://www . geesforgeks . org/node-js-process-uptime-method/](https://www.geeksforgeeks.org/node-js-process-uptime-method/)

**process.uptime()方法**是流程模块的内置应用编程接口，用于获取 Node.js 流程运行的秒数。

**语法:**

```
process.uptime();
```

**参数:**此方法不接受任何参数。

**返回值:**返回一个浮点数，指定 Node.js 进程运行的秒数。

下面的例子说明了在 Node.js 中 process.uptime()方法的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// process.uptime() Method

// Allocating process module
const process = require('process');

// Printing the number of seconds
// the Node.js process is running
console.log(process.uptime());
```

**输出:**

```
0.0842063
```

**例 2:**

```
// Node.js program to demonstrate the   
// process.uptime() Method

// Allocating process module
const process = require('process');

// Checking whether the method
// exists or not
if (process.uptime) {

    // Printing uptime() value
    console.log("The number of seconds the"
          + " Node.js process is running: "
          + process.uptime() + " seconds");

    var i = 1000000;

    while(i--);

    console.log("The number of seconds the"
          + " Node.js process is running: "
          + process.uptime() + " seconds");

    console.log("In whole seconds: "
          + Math.floor(process.uptime())
          + " seconds");
}
```

**输出:**

```
the number of seconds the Node.js process is running: 0.077 seconds
the number of seconds the Node.js process is running: 0.087 seconds
In whole seconds: 0 seconds

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_uptime