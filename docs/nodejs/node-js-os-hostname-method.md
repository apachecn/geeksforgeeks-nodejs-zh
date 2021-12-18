# node . js . OS . hostname()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-hostname-method/](https://www.geeksforgeeks.org/node-js-os-hostname-method/)

**os.hostname()方法**是 os 模块的内置应用编程接口，用于获取操作系统的主机名。

**语法:**

```
os.hostname()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个字符串值，指定操作系统的主机名。

下面的例子说明了 **os.hostname()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the    
// os.hostname() method 

// Allocating os module
const os = require('os');

// Printing os.hostname() value
console.log(os.hostname());
```

**输出:**

```
gekchos_lappy

```

**例 2:**

```
// Node.js program to demonstrate the    
// os.hostname() method 

// Allocating os module
const os = require('os');

// Printing os.hostname() value
if(os.hostname()) {
    var hostname = os.hostname();
    console.log("Hostname for the operating"
        + " system is " + String(hostname));
}
```

**输出:**

```
Hostname for the operating system is gekchos_lappy
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ hostname](https://nodejs.org/api/os.html#os_os_hostname)