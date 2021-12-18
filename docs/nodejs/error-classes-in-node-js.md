# node . js 中的错误类别

> 原文:[https://www.geeksforgeeks.org/error-classes-in-node-js/](https://www.geeksforgeeks.org/error-classes-in-node-js/)

Node.js 从 JavaScript < *Error* >类继承了 JavaScript 和系统错误，并保证提供该类可用的属性。使用由 JavaScript 提供的 ***try…catch*** 构造处理的抛出机制立即抛出错误的 JavaScript 异常。

Node.js 处理应用运行过程中出现的错误，支持多种错误机制，即如何报告和处理所有这些错误取决于 *Error* 类型和 *API* 风格。应用程序代码也会触发用户指定的错误。由 Node.js 生成的所有错误要么是实例，要么是从 Error 类继承的。在 Node.js 中，它在运行下面给出的应用程序时会遇到许多类型的错误:

**类:AssertionError:***AssertionErrors*由< *错误扩展而来。错误* >类。当它检测到一个异常的逻辑冲突已经发生，而这个逻辑冲突不应该发生时，这些错误就会被触发，断言模块就会引发所有这些错误。断言模块抛出的所有错误都是 *AssertionError* 类的实例。

**示例 1:文件名:index.js**

```
// Node.js program to demonstrate 
// Assertion error in JavaScript

// Importing Assert module
const assert = require('assert');

console.log("Throws Assertion Error...");

// Comparing equality using assert
assert.strictEqual(
    {'Alfa':'hi', 'beta':'hello'}, 
    {'Alfa':'hi', 'beta':'hello'}
);
// Throws AssertionError
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> **抛出断言错误**
> > >抛出断言错误……
> >>assert . js:101
> 抛出新的 AssertionError(obj)；
> AssertionError[ERR _ ASSERTION]:值具有相同的结构，但不等于引用:
> { Alfa: 'hi '，beta: 'hello'} at Object。<匿名>(C:\ Users \ Ajay Kumar \ Desktop \ test 2 . js:12:8)……。操作员:？[32m'strictEqual '？[3900 万]

**Class: RangeError:** 显示提供的参数不在可接受的值范围内。它可以是数字范围，也可以在选项集之外。

**示例 2:文件名:index.js**

```
// Node.js program to demonstrate 
// range error in JavaScript

// Importing http module
const http = require('http');

// Creating server with port no
// out of range
var server = http.createServer()
    .listen(46456656, (err, res)=>{
    // Throws Range Error
});
```

**输出:**

> **抛出范围错误**
> > >内部/验证器. js:192
> 抛出新的 ERR_SOCKET_BAD_PORT(名称，PORT)；
> 范围错误【ERR _ SOCKET _ BAD _ PORT】:options . PORT 应为> = 0 和< 65536。收到 46456656……代码:？[32m'ERR_SOCKET_BAD_PORT '？[3900 万]

**Class: ReferenceError:** 它指定没有定义任何人试图访问的变量。这种类型的错误指定了代码中的错别字或坏了的程序。*引用错误*的实例指定了代码中的一个错误，直到应用程序动态运行代码。

**示例 3:文件名:index.js**

```
// Node.js program to demonstrate 
// Reference error in JavaScript

try {
  const alfa = 10;
  const beta = alfa + gamma;

  // Throws with a ReferenceError 
  // because gamma is undefined
} catch (err) {
  console.log(err.message);
  console.log(err);

  // Handle the error here.
}
```

**输出:**

> **抛出参考错误**
> > >伽马未定义
> > >参考错误:伽马在对象处未定义
> 。<匿名>(C:\ Users \ Ajay Kumar \ Desktop \ test 2 . js:128:23)……在内部/main/run_main_module.js:17:47

**Class: SyntaxError:** 指定程序不是有效的 JavaScript，可能是代码求值的结果生成的。这些错误大多是由评估、函数、需求或虚拟机引起的。

**示例 4:文件名:index.js**

```
// Node.js program to demonstrate 
// Syntax error in JavaScript

try {

  // Import vm module
  require('vm').runInThisContext('alfa @ beta');
} catch (error) {

  // Prints a Syntax Error.
  console.log(error);
}
```

**输出:**

> **在新脚本(VM . js:99:7)……内部/main/run_main_module.js:17:47 处抛出语法错误**
> >>alfa @ beta
> >>语法错误:无效或意外标记

**类:系统错误:**由 Node.js 生成的系统错误是由于其运行时环境中的异常而发生的。当应用程序违反操作系统约束时，这些错误是可以预期的。

**示例 5:文件名:index.js**

```
// Node.js program to demonstrate 
// Reference error in JavaScript

// Importing fs module
const fs = require('fs');

// Callback function
function errorCallback(err, data) {
  if (err) {
    console.error('There was an error', err);
    return;
  }
  return(data);
}

// Trying to read file that does not exist
fs.readFile('/some/non-existing/file', errorCallback);
```

**输出:**

> **抛出错误**
> > >出现错误【错误:ENOENT:没有这样的文件或目录，打开' C:\某些\不存在的\文件' 】{
> errno: -4058，
> 代码:' ENOENT '，
> syscall: 'open '，
> 路径:' C:\某些\不存在的\ \文件' }

**类:类型错误:**它指定提供的参数不是允许的类型。例如，调用一个实际上不存在的函数将是一个类型错误。就像该表单是参数验证一样，它会立即引发类型错误实例。

**示例 6:文件名:index.js**

```
// Node.js program to demonstrate 
// Type error in JavaScript

try {
  if(1) {
    if(2) {
      console.loo('alfa')
    }
  }
} catch (error) {
console.log(error);  
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> **抛出类型错误**
> > >类型错误:console.loo 不是 Object 处的函数
> 。<匿名>(C:\ Users \ Ajay Kumar \ Desktop \ test 2 . js:104:15)……在内部/main/run_main_module.js:17:47

**参考:**T2