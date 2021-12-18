# Node.js process.cwd()方法

> 原文:[https://www.geeksforgeeks.org/node-js-process-cwd-method/](https://www.geeksforgeeks.org/node-js-process-cwd-method/)

**process.cwd()方法**是**流程模块**的内置应用编程接口，用于获取 node.js 流程的当前工作目录。

**语法:**

```js
process.cwd()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个指定 node.js 进程当前工作目录的字符串。

下面的例子说明了 **process.cwd()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// process.cwd() Method

// Include process module
const process = require('process');

// Printing current directory
console.log("Current working directory: ",
          process.cwd());
```

**输出:**

```js
Current working directory: C:\nodejs\g\process

```

**例 2:**

```js
// Node.js program to demonstrate the    
// process.cwd() Method

// Include process module
const process = require('process');

// Printing current directory
console.log("Current working directory: ",
          process.cwd());

try {

  // Change working directory
  process.chdir('../');
  console.log("Working directory after changing"
      + " directory: ", process.cwd());
} catch (err) {

  // printing error if occurs
  console.error("error occured while changing"
          + " directory: ", err);
}
```

**输出:**

```js
Current working directory: C:\nodejs\g\process
Working directory after changing directory: C:\nodejs\g\os

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2[https://nodejs.org/api/process.html#process_process_cwd](https://nodejs.org/api/process.html#process_process_cwd)