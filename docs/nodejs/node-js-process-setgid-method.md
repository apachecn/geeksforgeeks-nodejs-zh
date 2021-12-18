# Node.js process.setgid()方法

> 原文:[https://www . geesforgeks . org/node-js-process-setgid-method/](https://www.geeksforgeeks.org/node-js-process-setgid-method/)

**process.setgid()方法**是流程模块的内置应用编程接口，用于设置 Node.js 流程的组标识。
**语法:**

```
process.setgid(id)
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **id:** 它是一个必需的参数，包含一个字符串或一个整数，表示组名或标识，如果组名被传递，它会在解析相关的数字标识时阻塞。

**返回:**不返回值。
**注意:**这个功能只会在 POSIX 平台上工作。在 windows 或 android 平台上不可用，因此会导致错误，即 TypeError，setgid 不是函数。
以下示例说明了 **process.setgid()方法**在 Node.js:
**示例 1:** 中的使用

## java 描述语言

```
// Node.js program to demonstrate the    
// process.setgid() Method

// Including process module
const process = require('process');

// Printing the group identity of
// the Node.js process that checks
// whether the methods exists or not
if (process.getgid && process.setgid ) {

  // Setting gid
  process.setgid(400);

  // Printing getgid() value
  console.log("The group identity of the Node.js"
      + " process:", process.getgid());
}
```

**输出:**

```
The group identity of the Node.js process: 400
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the    
// process.setgid() Method

// Including process module
const process = require('process');

// Set gid and check whether the
// method exists or not
if (process.setgid) {

  // Within try catch
  try {
    process.setgid(696);
    console.log("gid has successfully been set");
  } catch (err) {
    console.log("Failed to set gid:", err);
  }
}

// Check whether the method exists or not
if (process.getgid) {

  // Printing getgid() value
  console.log("The group identity of the Node.js"
      + " process:", process.getgid());
}
```

**输出:**

```
gid has successfully been set
The group identity of the Node.js process: 696
```

**注意:**以上程序将使用 node filename.js 命令编译运行。
**参考:**[https://nodejs . org/API/process . html # process _ process _ setgid _ id](https://nodejs.org/api/process.html#process_process_setgid_id)