# Node.js process.setegid()方法

> 原文:[https://www . geesforgeks . org/node-js-process-setegid-method/](https://www.geeksforgeeks.org/node-js-process-setegid-method/)

**process.setegid()方法**是流程模块的内置应用编程接口，用于设置 Node.js 流程的数字有效组标识。

**语法:**

```js
process.setegid(id)
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **ID:** is required. It is a string or integer that represents the group name or ID. If the group name is passed, it will block when resolving the associated digital ID.

**返回:**不返回任何东西。

**注意:**此功能仅在 POSIX 平台上有效。在 windows 或 android 平台上不可用，因此会导致错误，即 TypeError，setegid 不是一个函数。

下面的例子说明了 **process.setegid()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// process.setegid() Method

// Include process module
const process = require('process');

// Printing the numerical effective group
// identity of the Node.js process checking
// whether the methods exists or not
if (process.getegid && process.setegid ) {

    // Setting gid
    process.setegid(400);

    // Printing getegid() value
  console.log("The numerical effective group"
        + " identity of the Node.js process:"
        + process.getegid());
}
```

**输出:**

```js
The numerical effective group identity of the Node.js process: 400

```

**例 2:**

```js
// Node.js program to demonstrate the   
// process.setegid() Method

// Include process module
const process = require('process');

// Checking whether the method
// exists or not
if (process.setegid) {
    try {
        process.setegid(696);
        console.log("gid has successfully been set");
      } catch (err) {
        console.log("Failed to set gid:", err);
      }
}

// Checking whether the method exists or not
if (process.getegid) {

    // Printing getegid() value
  console.log("The numerical effective group identity"
            + " of the Node.js process:"
            + process.getegid());
}
```

**输出:**

```js
gid has successfully been set
The numerical effective group identity of the Node.js process: 696

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**T2】https://nodejs.org/api/process.html#process_process_setegid