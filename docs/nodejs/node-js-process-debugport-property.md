# Node.js process.debugPort 属性

> 原文:[https://www . geesforgeks . org/node-js-process-debug port-property/](https://www.geeksforgeeks.org/node-js-process-debugport-property/)

**process.debugPort 属性**是进程模块的内置应用编程接口，用于获取调试器使用的调试端口(如果启用)。

**语法:**

```
process.debugPort
```

**返回值:**此属性返回一个整数值，指定调试器在启用时使用的调试端口。

下面的例子说明了 **process.debugPort 属性**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the    
// process.debugPort property

// Include process module
const process = require('process');

// Printing process.debugPort
console.log("debug port is " + process.debugPort);
```

**输出:**

```
debug port is 9229

```

**例 2:**

```
// Node.js program to demonstrate the    
// process.debugPort property

// Include process module
const process = require('process');

// Printing process.debugPort property value
var debug_port = process.debugPort;

// Check whether debug port is defined
if(debug_port != undefined){
    console.log("debug port is defined");
    console.log("debug port is " + debug_port);
}else{
    console.log("debug port is not defined");
}
```

**输出:**

```
debug port is defined
debug port is 9229

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ debug port](https://nodejs.org/api/process.html#process_process_debugport)