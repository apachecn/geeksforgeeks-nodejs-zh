# node . js process . setuncassetexceptioncapturecallback()方法

> 原文:[https://www . geeksforgeeks . org/node-js-process-setuncassetexceptioncapturecallback-method/](https://www.geeksforgeeks.org/node-js-process-setuncaughtexceptioncapturecallback-method/)

**process . setUncaptureexceptioncapturecallback()方法**是处理模块的一个内置应用编程接口，用于设置一个回调函数，当发生未捕获的异常时将调用该函数。回调函数将接收异常值作为其第一个参数。

**语法:**

```
process.setUncaughtExceptionCaptureCallback( callback_function )
```

**参数:**该方法接受如上所述的单个参数，如下所述。

*   **回调 _ 函数:**这是必选参数。它可以是一个函数或空值。如果设置为 null，那么函数将取消设置回调函数。

**返回:**不返回值。

以下示例说明了在 Node.js 中使用**process . setuncassetexceptioncapturecallback()方法**:

**例 1:**

## java 描述语言

```
// Allocating process module
const process = require('process');

// Function to be set as call back
function to_be_called(ex){
    console.log(ex);
}

// Checking whether any callback has been set before calling
// process.setUncaughtExceptionCaptureCallback(to_be_called);
console.log(process.hasUncaughtExceptionCaptureCallback());

// Setting callback
process.setUncaughtExceptionCaptureCallback(to_be_called);

// Checking whether any callback has been set before calling
// process.setUncaughtExceptionCaptureCallback(to_be_called);
console.log(process.hasUncaughtExceptionCaptureCallback());
```

**输出:**

```
false
true
```

**例 2:**

## java 描述语言

```
// Allocating process module
const process = require('process');

// Function to be set as call back
function to_be_called(ex) {
    console.log(ex);
}

// Checking whether any callback has been set before calling
// process.setUncaughtExceptionCaptureCallback(to_be_called);
// Printing whether a callback is set or not
if (process.hasUncaughtExceptionCaptureCallback()) {
    console.log("a callback has been set using " +
        "process.setUncaughtExceptionCaptureCallback() method");
} else {
    console.log("no callback has been set using " +
        "process.setUncaughtExceptionCaptureCallback() method");
}

// Setting callback
if (process.setUncaughtExceptionCaptureCallback) {
    process.setUncaughtExceptionCaptureCallback(to_be_called);
} else {
    console.log("process.setUncaughtExceptionCaptureCallback() "
        + "method is not defined!");
}

// Checking whether any callback has been set before calling
// process.setUncaughtExceptionCaptureCallback(to_be_called);
if (process.hasUncaughtExceptionCaptureCallback()) {
    console.log("a callback has been set using " +
        "process.setUncaughtExceptionCaptureCallback() method");
} else {
    console.log("no callback has been set using " +
        "process.setUncaughtExceptionCaptureCallback() method");
}

// Resetting callback
if (process.setUncaughtExceptionCaptureCallback) {
    process.setUncaughtExceptionCaptureCallback(null);
} else {
    console.log("process.setUncaughtExceptionCaptureCallback() "
        + " method is not defined!");
}

// Checking whether any callback has been set after resetting
if (process.hasUncaughtExceptionCaptureCallback()) {
    console.log("a callback has been set using " +
        "process.setUncaughtExceptionCaptureCallback() method");
} else {
    console.log("no callback has been set using " +
        "process.setUncaughtExceptionCaptureCallback() method");
}
```

**输出:**

```
no callback has been set using process.setUncaughtExceptionCaptureCallback() method
a callback has been set using process.setUncaughtExceptionCaptureCallback() method
no callback has been set using process.setUncaughtExceptionCaptureCallback() method
```

**注意:**以上程序将使用**节点 filename.js** 命令编译运行，仅在 POSIX 平台。

**参考:**[https://nodejs . org/API/process . html # process _ process _ setuncassetexceptioncapturecallback _ fn](https://nodejs.org/api/process.html#process_process_setuncaughtexceptioncapturecallback_fn)