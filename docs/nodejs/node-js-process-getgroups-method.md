# Node.js process.getgroups()方法

> 原文:[https://www . geesforgeks . org/node-js-process-getgroups-method/](https://www.geeksforgeeks.org/node-js-process-getgroups-method/)

**process.getgroups()方法**是 process 模块的内置应用编程接口，用于获取补充组标识。

**语法:**

```js
process.getgroups();
```

**参数:**此方法不接受任何参数。

**返回:**返回指定补充组标识的整数数组。

**注意:**此功能仅在 POSIX 平台上有效。在 windows 或 android 平台上不可用，因此会导致错误，即 TypeError， **getgroups** 不是一个函数。

下面的例子说明了 **process.getgroups()方法**在 Node.js 中的使用:

**例 1:**

```js
// Allocating process module
const process = require('process');

// Printing  the supplementary group IDs.
console.log(process.getgroups());
```

**输出:**

```js
[0]

```

**例 2:**

```js
// Allocating process module
const process = require('process');

// Checking whether the method exists or not
if (process.getgroups) {

    // Printing getgroups() values
  console.log("The supplementary group IDs :"
               + process.getgroups());
}
```

**输出:**

```js
The supplementary group IDs :[0]
```

**参考:**[https://nodejs . org/API/process . html # process _ process _ getgroups](https://nodejs.org/api/process.html#process_process_getgroups)