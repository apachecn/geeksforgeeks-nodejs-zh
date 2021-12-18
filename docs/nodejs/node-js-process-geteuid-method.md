# Node.js process.geteuid()方法

> 原文:[https://www . geesforgeks . org/node-js-process-geteuid-method/](https://www.geeksforgeeks.org/node-js-process-geteuid-method/)

**process.geteuid()方法**是流程模块的内置应用编程接口，用于获取 Node.js 流程的数值有效用户标识。

**语法:**

```
process.geteuid()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个对象，该对象指定 Node.js 进程的数字有效用户标识。

**注意:**这个方法只会在 POSIX 平台上工作。在 windows 或 android 平台上不可用，因此会导致错误，即 TypeError，geteuid 不是函数。

下面的例子说明了 **process.geteuid()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// process.geteuid() method  

// Include process module
const process = require('process');

// Printing the numerical effective
// user identity of the Node.js process
console.log(process.geteuid());
```

**输出:**

```
6693036

```

**例 2:**

```
// Node.js program to demonstrate the     
// process.geteuid() method  

// Include process module
const process = require('process');

// Check whether the method exists or not
if (process.geteuid) {

  // Printing geteuid() value
  console.log("The numerical effective user "
          + "identity of the Node.js process:"
          + process.geteuid());
}
```

**输出:**

```
The numerical effective user identity of the Node.js process: 6693036

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_geteuid