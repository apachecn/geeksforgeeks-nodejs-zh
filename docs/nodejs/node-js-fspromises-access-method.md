# Node.js fsPromises.access()方法

> 原文:[https://www . geesforgeks . org/node-js-fs promises-access-method/](https://www.geeksforgeeks.org/node-js-fspromises-access-method/)

**fsPromises.access()** 方法用于测试由*路径*指定的给定文件或目录的权限。要检查的权限可以使用文件访问常数指定为参数。还可以通过使用按位“或”运算符创建一个具有多个文件常量的掩码来检查多个文件权限。

如果可访问性检查成功，*承诺*被解析为无值。如果任何可访问性检查失败，*承诺*将被拒绝，并显示一个错误对象。

**语法:**

```js
fsPromises.access( path, mode )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address, which indicates the path of the file or directory whose permissions must be tested.
*   **mode:** is an integer value, indicating the authority to be tested. The logical or operator can be used to separate multiple permissions. It can have the values *fs.constants.f _ ok, fs.constants.R_OK, fs.constants.w _ ok* and *fs.constants.x _ ok* . This is an optional parameter. The default value is *fs.constants.f _ OK* .

**返回值:**返回*承诺。*

**示例 1:** 此示例显示了文件写权限的测试。

```js
// Node.js program to demonstrate the 
// fsPromises.access() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

// Allowing only read permission
fs.chmodSync("example_file.txt", fs.constants.R_OK); 

// Testing the write permission 
fsPromises.access('example_file.txt', fs.constants.W_OK)
.then(() => console.log('Can be accessed'))
.catch(() => console.error('Can not be accessed'));  
```

**输出:**

```js
Can not be accessed
```

**示例 2:** 此示例显示了文件读写权限的测试。

```js
// Node.js program to demonstrate the 
// fsPromises.access() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

// Allowing only read permission
console.log("Giving only read permission to the user"); 
fs.chmodSync("example_file.txt", fs.constants.R_OK); 

// Test the read permission 
fsPromises.access('example_file.txt', fs.constants.R_OK)
.then(() => console.log('Can be accessed'))
.catch(() => console.error('Can not be accessed'));

// Test both the read and write permissions 
fsPromises.access('example_file.txt', 
    fs.constants.R_OK | fs.constants.W_OK)
.then(() => console.log('Can be accessed'))
.catch(() => console.error('Can not be accessed'));
```

**输出:**

```js
Giving only read permission to the user
Can be accessed
Can not be accessed
```

不建议在调用 **fsPromises.open()** 之前使用 **fsPromises.access()** 检查文件的可访问性。这样做会引入竞争条件，因为其他进程可能会在两次调用之间改变文件的状态。相反，用户代码应该直接打开/读取/写入文件，并处理文件不可访问时引发的错误。