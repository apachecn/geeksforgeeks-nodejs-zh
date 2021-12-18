# Node.js process.setgroups()方法

> 原文:[https://www . geesforgeks . org/node-js-process-set groups-method/](https://www.geeksforgeeks.org/node-js-process-setgroups-method/)

**process.setgroups()方法**是流程模块的内置应用编程接口，用于设置补充组标识。

**语法:**

```js
process.setgroups( groups )
```

**参数:**该方法接受如上所述的单个参数，如下所述。

*   **Group:** This is a required parameter. An array of strings or integers, or both, indicate the group identification or group name or both.

**返回:**不返回任何东西。为了设置组标识，Node.js 进程需要根权限，因为它是一个特权操作。

**注意:**此功能仅在 POSIX 平台上有效。在 windows 或 android 平台上不可用，因此会导致错误，即类型错误，**设置组**不是功能。

下面的例子说明了 **process.setgroups()方法**在 Node.js 中的使用:

**例 1:**

```js
// Allocating process module
const process = require('process');

// Printing the supplementary group
// IDs before setting.
console.log(process.getgroups());

// Array of Group Ids
var arr=new Array(300, 400, 2000);

// Setting the supplementary group IDs.
process.setgroups(arr);

// Printing the supplementary group IDs.
console.log(process.getgroups());
```

**输出:**

```js
[ 0 ]
[ 300, 400, 2000, 0 ]
```

**例 2:**

```js
// Allocating process module
const process = require('process');

if (process.setgroups) {
    var arr=new Array(300, 400, 2000);

    // Setting the supplementary group IDs.
    process.setgroups(arr);
}

// Checking whether the method exists or not
if (process.getgroups) {

    // Printing getgroups()
  console.log("The supplementary group IDs :",
           process.getgroups());
}
```

**输出:**

```js
The supplementary group IDs : [ 300, 400, 2000, 0 ]
```

**注意:**以上程序将使用**节点 filename.js** 命令编译运行，仅在 POSIX 平台。

**参考:**[https://nodejs . org/API/process . html # process _ process _ set groups _ group](https://nodejs.org/api/process.html#process_process_setgroups_groups)