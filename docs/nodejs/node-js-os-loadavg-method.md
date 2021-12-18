# node . js . OS . loadavg()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-loadavg-method/](https://www.geeksforgeeks.org/node-js-os-loadavg-method/)

**os.loadavg()方法**是 os 模块的内置应用编程接口，用于获取负载平均值。负载平均值是系统活动的度量，用分数表示，由操作系统计算。

**语法:**

```
os.loadavg()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个数组，该数组包含大小为 3 的小数，表示操作系统计算的 1、5 和 15 分钟平均负载。在 windows 上，它将返回[0，0，0]，因为平均负载是 Unix 特有的概念。

下面的例子说明了 **os.loadavg()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the    
// os.loadavg() method 

// Run in Linux system
// Require os module
const os = require('os');

// Printing os.loadavg() value
console.log(os.loadavg());
```

**输出:**

```
[ 13.42041015625, 12.95166015625, 12.72509765625 ]

```

**例 2:**

```
// Node.js program to demonstrate the    
// os.loadavg() method 

// Run on Windows system
// Require os module
const os = require('os');

// Printing os.loadavg() value
console.log(os.loadavg());
```

**输出:**

```
[ 0, 0, 0 ]

```

**例 3:**

```
// Node.js program to demonstrate the    
// os.loadavg() method 

// Require os module
const os = require('os');

// Printing os.loadavg() value
var avg_load = os.loadavg();

console.log("Load average (1 minute):"
            + String(avg_load[0]));

console.log("Load average (5 minute):"
            + String(avg_load[1]));

console.log("Load average (15 minute):"
            + String(avg_load[2]));
```

**输出:**

```
Load average (1 minute):15.87158203125
Load average (5 minute):14.193359375
Load average (15 minute):13.365234375

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ load avg](https://nodejs.org/api/os.html#os_os_loadavg)