# Node.js os.homedir()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-homedir-method/](https://www.geeksforgeeks.org/node-js-os-homedir-method/)

**os.homedir()方法**是 os 模块内置的应用编程接口，用于获取当前用户的主目录路径。

**语法:**

```js
os.homedir()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回一个字符串，指定当前用户主目录的路径。

*   On windows, it collects its value from an environment variable named `USERPROFILE` (if defined). Otherwise, it returns the path of the current user's profile directory.
*   On POSIX, it collects its value from an environment variable named `$HOME` (if defined). Otherwise, it will return the home directory of a valid UID.

下面的例子说明了 **os.homedir()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// os.homedir() method

// Allocating os module
const os = require('os');

// Printing os.homedir() value
console.log(os.homedir());
```

**输出:**

```js
C:\Users\gekcho

```

**示例 2:** 替代方式查找主目录

```js
// Node.js program to demonstrate the   
// os.homedir() method

// Allocating os module
const os = require('os');

console.log(getUserHome());

function getUserHome() {

    // Return the value using process.env
    return process.env[(process.platform == 
          'win32') ? 'USERPROFILE' : 'HOME'];
}
```

**输出:**

```js
C:\Users\gekcho

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考资料:**[https://nodejs . org/API/OS . html # OS _ OS _ home dir](https://nodejs.org/api/os.html#os_os_homedir)