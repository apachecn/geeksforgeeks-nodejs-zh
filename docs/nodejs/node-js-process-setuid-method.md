# Node.js process.setuid()方法

> 原文:[https://www . geesforgeks . org/node-js-process-setuid-method/](https://www.geeksforgeeks.org/node-js-process-setuid-method/)

**process.setuid()方法**是流程模块的内置应用编程接口，用于设置 Node.js 流程的用户身份。

**语法:**

```
process.setuid(id)
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **id:** 它是一个必需的参数，包含一个字符串或一个整数，表示数字 id 或用户名字符串，如果用户名被传递，它会在解析相关数字 ID 时阻塞。

**返回:**不返回值。

**注意:**此功能仅在 POSIX 平台上有效。在 windows 或 android 平台上不可用，因此会导致错误，即 TypeError，setuid 不是函数。

下面的例子说明了 **process.setuid()方法**在 Node.js 中的使用:

**例 1:**

## java 描述语言

```
// Node.js program to demonstrate the     
// process.setuid() Method

// Including process module
const process = require('process');

// Print the user identity of the Node.js
//  process and check whether the methods
// exists or not
if (process.getuid && process.setuid ) {

  // Setting user id
  process.setuid(400);

  // Printing getuid() value
  console.log("The user identity of the Node.js"
      + " process:", process.getuid());
}
```

**输出:**

```
The user identity of the Node.js process: 400
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the     
// process.setuid() Method

// Including process module
const process = require('process');

// Sett user id and check whether
// the method exists or not
if (process.setuid) {

  // Within try catch
  try {
    process.setuid(696);
    console.log("User id has successfully been set");
  } catch (err) {
    console.log("Failed to set user id:", err);
  }
}

// Check whether the method exists or not
if (process.getuid) {

  // Printing getuid() value
  console.log("The user identity of the Node.js"
        + " process:", process.getuid());
}
```

**输出:**

```
User id has successfully been set
The user identity of the Node.js process: 696
```

**注意:**以上程序将使用 node filename.js 命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ setuid _ id](https://nodejs.org/api/process.html#process_process_setuid_id)