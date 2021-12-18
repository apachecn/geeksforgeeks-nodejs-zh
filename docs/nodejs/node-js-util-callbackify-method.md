# Node.js util.callbackify()方法

> 原文:[https://www . geesforgeks . org/node-js-util-callbackify-method/](https://www.geeksforgeeks.org/node-js-util-callbackify-method/)

**util.callbackify()方法**是 util 模块的内置应用编程接口，用于运行异步函数并在 node.js.
中获取回调**语法:**

```
util.callbackify( async_function )
```

**参数:**该方法接受如上所述和如下所述的单个参数。

*   **async_function:** 是必需参数，表示原始的异步函数。

**返回值:**作为错误优先回调风格函数返回承诺。其以(err，ret) = > {}为参数，第一个参数为错误或拒绝原因，可能为 null(当承诺被解析时)，第二个参数为解析值。
以下示例说明了 Node.js 中 util.callbackify()方法的使用:
**示例 1:**

## java 描述语言

```
// Node.js program to demonstrate the   
// util.callbackify() Method 

// Allocating util module
const util = require('util');

// Async function to be called
// from util.callbackify() method
async function async_function() {
    return 'message from async function';
}

// Calling callbackify()
const callback_function = 
        util.callbackify(async_function);

// Listener for callback_function
callback_function((err, ret) => {
    if (err) throw err;
    console.log(ret);
});
```

**输出:**

```
message from async function
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the   
// util.callbackify() Method 

// Allocating util module
const util = require('util');

// Async function to be called 
// from util.callbackify() method
async function async_function() {
    return Promise.reject(new Error(
        'this is an error message!'));
}

// Calling callbackify()
const callback_function =
    util.callbackify(async_function);

// Listener for callback_function
callback_function((err, ret) => {

    // If error occurs
    if (err && err.hasOwnProperty('reason')
        && err.reason === null) {

        // Printing error reason
        console.log(err.reason);
    } else {
        console.log(err);
    }
});
```

**输出:**

```
Error: this is an error message!
    at async_function (C:\nodejs\g\util\callbackify_2.js:6:25)
    at async_function (util.js:356:13)
    at Object. (C:\nodejs\g\util\callbackify_2.js:12:1)
    at Module._compile (internal/modules/cjs/loader.js:776:30)
    at Object.Module._extensions..js (internal/modules/cjs/loader.js:787:10)
    at Module.load (internal/modules/cjs/loader.js:653:32)
    at tryModuleLoad (internal/modules/cjs/loader.js:593:12)
    at Function.Module._load (internal/modules/cjs/loader.js:585:3)
    at Function.Module.runMain (internal/modules/cjs/loader.js:829:12)
    at startup (internal/bootstrap/node.js:283:19)
```

**注意:**以上程序将使用 node filename.js 命令编译运行。
**参考:**[https://nodejs . org/API/util . html # util _ util _ callbackify _ original](https://nodejs.org/api/util.html#util_util_callbackify_original)