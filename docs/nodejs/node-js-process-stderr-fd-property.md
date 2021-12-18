# node . js process . stderr . FD Property

> 原文:[https://www . geesforgeks . org/node-js-process-stderr-FD-property/](https://www.geeksforgeeks.org/node-js-process-stderr-fd-property/)

**process.stderr.fd** 是 process 模块内 Process 类的内置应用编程接口，用于返回 process.stderr 的底层文件描述符的值。

**语法:**

```
const process.stderr.fd
```

**参数:**该 api 不接受任何参数作为参数。

**返回值:**这个 api 返回 process.stderr 的底层文件描述符的值。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// process.stderr.fd

// Importing process module
const process = require('process');

// Getting the value of file descriptor 
// by using process.stderr.fd
const value = process.stderr.fd

// Display the result
console.log(value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
2
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// process.stderr.fd

// Importing process module
const process = require('process');

// Updating file descriptor value
process.stderr.fd = 10

// Getting the value of file descriptor 
// by using process.stderr.fd
const value = process.stderr.fd

// Display the result
console.log(value)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
10
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ process _ stderr _ FD](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_stderr_fd)