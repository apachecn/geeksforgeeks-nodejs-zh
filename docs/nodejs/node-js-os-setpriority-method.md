# Node.js os.setPriority()方法

> 原文:[https://www . geesforgeks . org/node-js-OS-set priority-method/](https://www.geeksforgeeks.org/node-js-os-setpriority-method/)

**os.setPriority()方法**是 os 模块内置的应用编程接口，用于设置 pid 和优先级指定的进程调度优先级。

**语法:**

```js
os.setPriority(pid, priority)
```

**参数:**该方法有两个参数，如上所述，描述如下:

*   **pid:** 是可选参数。它指定要设置调度优先级的进程 id。其默认值为 0。
*   **优先级:**是必选参数。它指定为进程指定的进程 id 设置的优先级。此参数的值必须介于-20(最高)到 19(最低)之间。

**返回值:**这个方法不返回任何东西。

**注意:**由于 windows 系统中的优先级不同于 UNIX 系统，因此 Windows 系统中的优先级被映射到 os.constants.priority 中的六个优先级常量之一。因此，在检索时，该值可能与实际值略有不同。在 windows 系统中，为了设置最高优先级，我们需要提升用户权限。因此，有时优先级最高可能会在没有任何警告的情况下被更改为优先级高。

下面的例子说明了 os.setPriority()方法在 Node.js 中的使用:

**例 1:**

## java 描述语言

```js
// Node.js program to demonstrate the   
// os.setPriority() Method

// Allocating os module
const os = require('os');

// Setting priority for the current process
console.log("setting priority for"
    + " the current process to 17");
try{
    // Setting priority of current process
    os.setPriority(17);
}catch(err){
    // Printing error message if any
    console.log(": error occurred"+err);
}
```

**输出:**

```js
setting priority for the current process to 17
```

**例 2:**

## java 描述语言

```js
// Node.js program to demonstrate the   
// os.setPriority() Method

// Allocating os module
const os = require('os');

// Setting priority for the current process
os.setPriority(17);

try{
    // Printing priority of current process
    console.log(os.getPriority());
}catch(err){
    // Printing error message
    console.log(": error occurred"+err);
}
```

**输出:**

```js
10
```

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ set priority _ PID _ priority](https://nodejs.org/api/os.html#os_os_setpriority_pid_priority)T4】