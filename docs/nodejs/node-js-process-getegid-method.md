# Node.js process.getegid()方法

> 原文:[https://www . geesforgeks . org/node-js-process-getegid-method/](https://www.geeksforgeeks.org/node-js-process-getegid-method/)

**process.getegid()方法**是流程模块的内置应用编程接口，用于获取 Node.js 流程的数字有效组标识。

**语法:**

```js
process.getegid()
```

**参数:**此方法不接受任何参数。

**返回值:**返回一个指定 Node.js 进程的数字有效组标识的对象。

**注意:**此功能仅在 POSIX 平台上有效。在 windows 或 android 平台上不可用，因此会导致错误，即 TypeError，getegid 不是函数。

下面的例子说明了 **process.getegid()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// process.getegid() Method

// Include process module
const process = require('process');

// Print the numerical effective group
// identity of the Node.js process
console.log(process.getegid());
```

**输出:**

```js
0
```

**例 2:**

```js
// Node.js program to demonstrate the     
// process.getegid() Method

// Include process module
const process = require('process');

// Check whether the method exists or not
if (process.getegid) {

  // Printing getegid() value
  console.log("The numerical effective group"
        + " identity of the Node.js process:"
        + process.getegid());
}
```

**输出:**

```js
The numerical effective group identity of the Node.js process: 0

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_getegid