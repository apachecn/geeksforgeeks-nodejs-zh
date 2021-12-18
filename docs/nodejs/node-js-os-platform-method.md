# node . js . OS . platform()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-platform-method/](https://www.geeksforgeeks.org/node-js-os-platform-method/)

**os.platform()方法**是 os 模块的内置应用编程接口，用于获取操作系统平台。

**语法:**

```
os.platform()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法返回一个代表操作系统平台的字符串。返回值可以是“aix”、“android”、“darwin”、“freebsd”、“linux”、“openbsd”、“sunos”和“win32”中的一个。该值在编译时设置。
以下示例说明了 **os.platform()方法**在 Node.js:
**示例 1:** 中的使用

## java 描述语言

```
// Node.js program to demonstrate the    
// os.platform() method 

// Require os module
const os = require('os');

// Printing os.platform() value
console.log(os.platform());
```

**输出:**

```
linux
```

**例 2:** 本例为第一例的替代例。

## java 描述语言

```
// Node.js program to demonstrate the    
// os.platform() method
console.log(process.platform);
```

**输出:**

```
linux
```

**例 3:**

## java 描述语言

```
// Node.js program to demonstrate the    
// os.platform() method 

// Require os module
const os = require('os');

// Printing os.platform() value
var platform = os.platform();

switch(platform) {
    case 'aix': console.log("IBM AIX platform");
        break;
    case 'android': console.log("Android platform");
        break;
    case 'darwin': console.log("Darwin platform(MacOS, IOS etc)");
        break;
    case 'freebsd': console.log("FreeBSD Platform");
        break;
    case 'linux': console.log("Linux Platform");
        break;
    case 'openbsd': console.log("OpenBSD platform");
        break;
    case 'sunos': console.log("SunOS platform");
        break;
    case 'win32': console.log("windows platform");
        break;    
    default: console.log("unknown platform");
}
```

**输出:**

```
Linux Platform
```

**注意:**以上程序将使用 node index.js 命令编译运行。
T3【参考:T5【https://nodejs.org/api/os.html#os_os_platform】T6