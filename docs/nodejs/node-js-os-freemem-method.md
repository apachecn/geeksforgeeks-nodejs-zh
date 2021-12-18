# node . js . OS . freemem()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-freemem-method/](https://www.geeksforgeeks.org/node-js-os-freemem-method/)

**os.freemem()方法**是 os 模块的内置应用编程接口，用于获取系统空闲内存量。

**语法:**

```js
os.freemem()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个整数值，以字节为单位指定可用系统内存量。

下面的例子说明了 **os.freemem()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// os.freemem() method

// Allocating os module
const os = require('os');

// Printing os.freemem() value
console.log(os.freemem());
```

**输出:**

```js
4158910464

```

**例 2:**

```js
// Node.js program to demonstrate the   
// os.freemem() method

// Allocating os module
const os = require('os');

// Printing os.freemem() value
var free_memory = os.freemem();
var free_mem_in_kb = free_memory/1024;
var free_mem_in_mb = free_mem_in_kb/1024;
var free_mem_in_gb = free_mem_in_mb/1024;

free_mem_in_kb = Math.floor(free_mem_in_kb);
free_mem_in_mb = Math.floor(free_mem_in_mb);
free_mem_in_gb = Math.floor(free_mem_in_gb);

free_mem_in_mb = free_mem_in_mb%1024;
free_mem_in_kb = free_mem_in_kb%1024;
free_memory = free_memory%1024;

console.log("Free memory: " + free_mem_in_gb + "GB "
      + free_mem_in_mb + "MB " + free_mem_in_kb
      + "KB and " + free_memory + "Bytes");
```

**输出:**

```js
Free memory: 4GB 110MB 88KB and 0Bytes

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考资料:**[https://nodejs . org/API/OS . html # OS _ OS _ free mem](https://nodejs.org/api/os.html#os_os_freemem)