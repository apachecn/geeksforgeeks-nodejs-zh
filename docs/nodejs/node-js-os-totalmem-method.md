# node . js . OS . totalmem()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-totalmem-method/](https://www.geeksforgeeks.org/node-js-os-totalmem-method/)

**os.totalmem()方法**是 os 模块的内置应用编程接口，用于获取系统内存总量(以字节为单位)。

**语法:**

```js
os.totalmem()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个整数值，以字节为单位指定系统内存总量。

下面的例子说明了 **os.totalmem()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// os.totalmem() method 

// Import the os module
const os = require('os');

// Printing os.totalmem() method value
console.log(os.totalmem());
```

**输出:**

```js
8502722560
```

**例 2:**

```js
// Node.js program to demonstrate the    
// os.totalmem() method 

// Import the os module
const os = require('os');

// Convert total memory to kb, mb and gb
var total_memory = os.totalmem();
var total_mem_in_kb = total_memory/1024;
var total_mem_in_mb = total_mem_in_kb/1024;
var total_mem_in_gb = total_mem_in_mb/1024;

total_mem_in_kb = Math.floor(total_mem_in_kb);
total_mem_in_mb = Math.floor(total_mem_in_mb);
total_mem_in_gb = Math.floor(total_mem_in_gb);

total_mem_in_mb = total_mem_in_mb%1024;
total_mem_in_kb = total_mem_in_kb%1024;
total_memory = total_memory%1024;

// Display memory size
console.log("Total memory: " + total_mem_in_gb + "GB "
          + total_mem_in_mb + "MB " + total_mem_in_kb
          + "KB and " + total_memory + "Bytes");
```

**输出:**

```js
Total memory: 7GB 940MB 848KB and 0Bytes

```

**例 3:**

```js
// Node.js program to demonstrate the    
// os.totalmem() method 

// Import the os module
const os = require('os');

// Printing free memory out of total memory
console.log("Free Memory " + String(os.freemem())
    + " Bytes out of " + String(os.totalmem()) + " Bytes");
```

**输出:**

```js
Free Memory 4161896448 Bytes out of 8502722560 Bytes

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ total mem](https://nodejs.org/api/os.html#os_os_totalmem)