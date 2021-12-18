# 节点. js 流程.平台属性

> 原文:[https://www . geesforgeks . org/node-js-process-platform-property/](https://www.geeksforgeeks.org/node-js-process-platform-property/)

**进程平台属性**是进程模块的内置应用编程接口，用于获取操作系统平台信息。

**语法:**

```
process.platform
```

**返回值:**这个属性返回一个代表操作系统平台的字符串。返回值可以是“aix”、“android”、“darwin”、“freebsd”、“linux”、“openbsd”、“sunprocess”和“win32”中的一个。该值在编译时设置。

下面的例子说明了**流程平台属性**在 Node.js 中的使用:

**例 1:**

## java 描述语言

```
// Node.js program to demonstrate the
// process.platform Property

// Include process module
const process = require('process');

// Printing process.platform property value
console.log(process.platform);
```

**输出:**

```
win32
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the
// process.platform Property

// Include process module
const process = require('process');

// Printing process.platform property value
var platform = process.platform;
switch(platform) {
    case 'aix': 
        console.log("IBM AIX platform");
        break;
    case 'darwin': 
        console.log("Darwin platform(MacOS, IOS etc)");
        break;
    case 'freebsd': 
        console.log("FreeBSD Platform");
        break;
    case 'linux': 
        console.log("Linux Platform");
        break;
    case 'openbsd': 
        console.log("OpenBSD platform");
        break;
    case 'sunos': 
        console.log("SunOS platform");
        break;
    case 'win32':
        console.log("windows platform");
        break;    
    default: 
        console.log("unknown platform");
}
```

**输出:**

```
windows platform
```

**注意:**以上程序将使用 node filename.js 命令编译运行。
**参考:**[https://nodejs . org/API/process . html # process _ process _ platform](https://nodejs.org/api/process.html#process_process_platform)