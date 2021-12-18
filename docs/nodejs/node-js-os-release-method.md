# node . js . OS . release()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-release-method/](https://www.geeksforgeeks.org/node-js-os-release-method/)

**os.release()方法**是 os 模块的内置应用编程接口，用于获取操作系统版本。

**语法:**

```
os.release()
```

**参数:**此方法不接受任何参数。
**返回值:**这个方法返回一个代表操作系统版本的字符串。

下面的例子说明了 **os.release()方法**在 Node.js 中的使用:

**例 1:**

## java 描述语言

```
// Node.js program to demonstrate the    
// os.release() method 

// Allocating os module
const os = require('os');

// Printing os.release() value
console.log(os.release());
```

**输出:**在 windows 系统上

```
10.0.17763
```

**输出:**在 Linux 系统上

```
3.10.0-1062.1.1.el7.x86_64
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the    
// os.release() method 

// Allocating os module
const os = require('os');

// Printing os.platform() value
var platform = os.platform();
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
        console.log("Windows platform");
        break;    
    default: 
        console.log("Unknown platform");
}

// Printing version 
console.log("Version: " + os.release());
```

**输出:**

```
Windows platform
Version: 10.0.17763
```

**注意:**以上程序将使用 node index.js 命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ release](https://nodejs.org/api/os.html#os_os_release)