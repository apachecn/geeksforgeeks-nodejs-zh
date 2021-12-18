# Node.js | os.tmpdir()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-tmpdir-method/](https://www.geeksforgeeks.org/node-js-os-tmpdir-method/)

**os.tmpdir()方法**是 os 模块内置的应用编程接口，用于获取操作系统临时文件的默认目录路径。

**语法:**

```js
os.tmpdir()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回一个字符串，指定操作系统临时文件默认目录的路径。

下面的例子说明了 os.tmpdir()方法在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// os.tmpdir() method 

// Allocating os module
const os = require('os');

// Display os.tmpdir() value
console.log(os.tmpdir());
```

**输出:**

```js
C:\Users\gekcho\AppData\Local\Temp

```

**例 2:**

```js
// Node.js program to demonstrate the    
// os.tmpdir() method 

// Allocating os module
const os = require('os');

console.log("home directory:" + getUserHome());
console.log("temp directory:" + os.tmpdir());

function getUserHome() {

    // From process.env
    return process.env[(process.platform == 'win32')
            ? 'USERPROFILE' : 'HOME'];
}
```

**输出:**

```js
home directory:C:\Users\gekcho
temp directory:C:\Users\gekcho\AppData\Local\Temp

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考资料:**[https://nodejs . org/API/OS . html # OS _ OS _ tmpdir](https://nodejs.org/api/os.html#os_os_tmpdir)