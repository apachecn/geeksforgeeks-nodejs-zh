# node . js process . hasuncutexceptioncapturecallback()方法

> 原文:[https://www . geeksforgeeks . org/node-js-process-hasuncassetexceptioncapturecallback-method/](https://www.geeksforgeeks.org/node-js-process-hasuncaughtexceptioncapturecallback-method/)

**process . hasuncassetexceptioncapturecallback()方法**是流程模块的内置应用编程接口，用于获取是否使用 process . setuncassetexceptioncapturecallback()方法设置了回调。

**语法:**

```
process.hasUncaughtExceptionCaptureCallback()
```

**参数:**此方法不接受任何参数。
**返回值:**返回一个布尔值，该值指定是否使用 process . setuncassetexceptioncapturecallback()设置了回调。

以下示例说明了在 Node.js 中使用**process . hasuncassetexceptioncapturecallback()方法**:

**例 1:**

## java 描述语言

```
// Node.js program to demonstrate the   
// process.hasUncaughtExceptionCaptureCallback() Method

// Include process module
const process = require('process');

console.log(process.hasUncaughtExceptionCaptureCallback());

// Printing whether a callback is set or not
if(process.hasUncaughtExceptionCaptureCallback()) {
    console.log("A callback has been set using "
    + "process.setUncaughtExceptionCaptureCallback() method");
}else{
        console.log("No callback has been set using "
        + "process.setUncaughtExceptionCaptureCallback() method");
}
```

**输出:**

```
false
No callback has been set using process.setUncaughtExceptionCaptureCallback() method
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the   
// process.hasUncaughtExceptionCaptureCallback() Method

// Include process module
const process = require('process');

function to_be_called(ex){
    console.log(ex);
}

// Setting callback 
process.setUncaughtExceptionCaptureCallback(to_be_called);

console.log(process.hasUncaughtExceptionCaptureCallback());

// Printing whether a callback is set or not
if(process.hasUncaughtExceptionCaptureCallback()){
    console.log("A callback has been set using "
    + "process.setUncaughtExceptionCaptureCallback() method");
}else{
    console.log("No callback has been set using "
    + "process.setUncaughtExceptionCaptureCallback() method");
}
```

**输出:**

```
true
A callback has been set using process.setUncaughtExceptionCaptureCallback() method
```

**注意:**以上程序将使用 node filename.js 命令编译运行。
**参考:**[https://nodejs . org/API/process . html # process _ process _ hasunchargetexceptioncapturecallback](https://nodejs.org/api/process.html#process_process_hasuncaughtexceptioncapturecallback)