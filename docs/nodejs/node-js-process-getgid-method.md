# Node.js process.getgid()方法

> 原文:[https://www . geesforgeks . org/node-js-process-getgid-method/](https://www.geeksforgeeks.org/node-js-process-getgid-method/)

**process.getgid()方法**是流程模块的内置应用编程接口，用于获取 Node.js 流程的数字组标识。

**语法:**

```js
process.getgid()
```

**参数:**此方法不接受任何参数。

**返回值:**返回一个指定 Node.js 进程的数字组标识的对象。

**注意:**这个方法只会在 POSIX 平台上工作。在 windows 或 android 平台上不可用，因此会导致错误，即 TypeError，getgid 不是函数。

下面的例子说明了 **process.getgid()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// process.getgid() method  

// Include process module
const process = require('process');

// Printing the numerical group
// identity of the Node.js process
console.log(process.getgid());
```

**输出:**

```js
1000

```

**例 2:**

```js
// Node.js program to demonstrate the     
// process.getgid() method  

// Include process module
const process = require('process');

// Checking whether this method
// exists or not
if (process.getgid) {

  // Printing getgid() value
  console.log("The numerical group identity "
              + "of the Node.js process: "
              + process.getgid());
}
```

**输出:**

```js
The numerical group identity of the Node.js process: 1000

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_getgid