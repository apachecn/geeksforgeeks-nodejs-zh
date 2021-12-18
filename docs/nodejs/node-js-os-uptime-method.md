# node . js . OS . uptime()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-uptime-method/](https://www.geeksforgeeks.org/node-js-os-uptime-method/)

**os.uptime()方法**是 os 模块的内置应用编程接口，用于以秒为单位获取系统正常运行时间。

**语法:**

```
os.uptime()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个整数值，指定系统运行的秒数，即系统正常运行时间。

下面的例子说明了 **os.uptime()方法**在 Node.js 中的使用:

**例 1:**

## java 描述语言

```
// Node.js program to demonstrate the    
// os.uptime() method 

// Allocating os module
const os = require('os');

// Printing os.uptime() value
console.log(String(os.uptime()) + " Seconds");
```

**输出:**

```
4507 Seconds
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the    
// os.uptime() method 

// Allocating os module
const os = require('os');

// Printing os.uptime() value
var ut_sec = os.uptime();
var ut_min = ut_sec/60;
var ut_hour = ut_min/60;

ut_sec = Math.floor(ut_sec);
ut_min = Math.floor(ut_min);
ut_hour = Math.floor(ut_hour);

ut_hour = ut_hour%60;
ut_min = ut_min%60;
ut_sec = ut_sec%60;

console.log("Up time: " 
        + ut_hour + " Hour(s) " 
        + ut_min + " minute(s) and " 
        + ut_sec + " second(s)");
```

**Output:**

```
Up time: 1 Hour(s) 18 minute(s) and 8 second(s)
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考资料:**[https://nodejs . org/API/OS . html # OS _ OS _ uptime](https://nodejs.org/api/os.html#os_os_uptime)