# node . js OS . CPU()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-cpus-method/](https://www.geeksforgeeks.org/node-js-os-cpus-method/)

**os . CPU()方法**是 OS 模块的内置应用编程接口，用于获取计算机每个逻辑 CPU 内核的信息。

**语法:**

```
os.cpus()
```

**参数:**此方法不接受任何参数。

**Return:** 这个方法返回一个包含每个逻辑 CPU 核心信息的对象。每个返回的对象将包含以下属性:

*   **Model:** A string that specifies the CPU kernel model.
*   **Speed:** A number that specifies the CPU core speed (in megahertz).
*   **Time:** Objects with the following attributes:
    *   **User:** A number specifies the time (in milliseconds) spent by the CPU in user mode.
    *   **nice:** A number specifies the time spent by the CPU in nice mode, in milliseconds.
    *   **sys:** A number specifies the time spent by CPU in sys mode, in milliseconds.
    *   **idle:** A number specifies the time spent by the CPU in idle mode, in milliseconds.
    *   **irq:** A number that specifies the time spent by the CPU in IRQ mode, in milliseconds.

**注意:**`nice`值仅用于 POSIX。在 Windows 操作系统上，所有处理器的`nice`值始终为 0。

下面的例子说明了**OS . CPU()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// os.cpus() method

// Allocating os module
const os = require('os');

// Printing os.cpus() values
console.log(os.cpus());
```

**输出:**

```
[ { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 900000, nice: 0, sys: 940265, idle: 11928546, irq: 147046 } },
  { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 860875, nice: 0, sys: 507093, idle: 12400500, irq: 27062 } },
  { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 1273421, nice: 0, sys: 618765, idle: 11876281, irq: 13125 } },
  { model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
    speed: 2712,
    times:
     { user: 943921, nice: 0, sys: 460109, idle: 12364453, irq: 12437 } } ]

```

**例 2:**

```
// Node.js program to demonstrate the   
// os.cpus() method

// Allocating os module
const os = require('os');

// Printing os.cpus()
var cpu_s=os.cpus();
var no_of_logical_core=0;
cpu_s.forEach(element => { 
    no_of_logical_core++;
    console.log("Logical core "
            + no_of_logical_core + " :");
    console.log(element); 
}); 

console.log("total number of logical core is "
        + no_of_logical_core);
```

**输出:**

```
Logical core 1 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 856437, nice: 0, sys: 866203, idle: 11070046, irq: 133562 } }
Logical core 2 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 805296, nice: 0, sys: 462656, idle: 11524406, irq: 23218 } }
Logical core 3 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 1225062, nice: 0, sys: 566421, idle: 11000875, irq: 12203 } }
Logical core 4 :
{ model: 'Intel(R) Core(TM) i5-7200U CPU @ 2.50GHz',
  speed: 2712,
  times:
   { user: 900234, nice: 0, sys: 420000, idle: 11472125, irq: 11781 } }
total number of logical core is 4

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ CPU](https://nodejs.org/api/os.html#os_os_cpus)