# Node.js fs.mkdtempSync()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-mkdtempsync-method/](https://www.geeksforgeeks.org/node-js-fs-mkdtempsync-method/)

**fs.mkdtempSync()方法**是 fs 模块的内置应用程序编程接口，它提供了一个应用编程接口，用于以一种围绕标准 POSIX 函数紧密建模的方式与文件系统交互。fs.mkdtempSync()方法创建一个唯一的临时目录。这是 fs.mkdtemp()方法的同步版本。

**语法:**

```js
fs.mkdtempSync( prefix, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Prefix:** Attach six random characters to the prefix to create a unique temporary directory.
*   **Option:** Optional parameter, which can be a character string with specified code or an object with code attribute, and specify the character code to be used.

**返回值:**返回创建的文件夹路径。

下面的例子说明了 **fs.mkdtempSync()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// fs.mkdtempSync() method    

// It includes fs module         
const fs = require('fs');    

// It includes os module         
const os = require('os');    

// It includes path module         
const path = require('path');

// Return the created folder
console.log(fs.mkdtempSync(
    path.join(os.tmpdir(), 'foo-')));
```

**输出:**

```js
/tmp/foo-OkEvul

```

**例 2:**

```js
// Node.js program to demonstrate the    
// fs.mkdtempSync() method    

// It includes fs module         
const fs = require('fs');

// It includes os module
const os = require('os');

const tmpDir = os.tmpdir();

const { sep } = require('path');

// Print something similar to `/tmp/abc123`.
// A new temporary directory is created within
// the /tmp directory.
console.log(fs.mkdtempSync(`${tmpDir}${sep}`));
```

**输出:**

```js
/tmp/bGVto1
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ mkdtmpsync _ prefix _ options](https://nodejs.org/api/fs.html#fs_fs_mkdtempsync_prefix_options)