# Node.js fs.accessSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-accesssync-method/](https://www.geeksforgeeks.org/node-js-fs-accesssync-method/)

**fs.accessSync()方法**用于同步测试给定文件或目录的权限。要检查的权限可以使用文件访问常数指定为参数。还可以通过使用按位“或”运算符创建一个具有多个文件常量的掩码来检查多个文件权限。

**语法:**

```js
fs.accessSync( path, mode )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address, which indicates the path of the file or directory whose permissions must be tested.
*   **Mode:** indicates an integer value requiring test permission. The logical or operator can be used to separate multiple permissions. It can have values `fs.constants.F_OK`, `fs.constants.R_OK`, `fs.constants.W_OK` and `fs.constants.X_OK`. This is an optional parameter. The default value is `fs.constants.F_OK`.

下面的例子说明了 Node.js 中的 **fs.accessSync()方法**:

**示例 1:** 此示例显示了文件读写权限的测试。

```js
// Node.js program to demonstrate the
// fs.accessSync() method

// Import the filesystem module
const fs = require('fs');

// Allowing only read permission
console.log("Giving only read permission to user");
fs.chmodSync("example.txt", fs.constants.S_IRUSR);

// Test the read permission
console.log('\n> Checking Permission for reading the file');
try {
  fs.accessSync('example.txt', fs.constants.R_OK);
  console.log('File can be read');
} catch (err) {
  console.error('No Read access');
}

// Test both the read and write permission
console.log('\n> Checking Permission for reading and writing to file');
try {
  fs.accessSync('example.txt', fs.constants.R_OK | fs.constants.W_OK);
  console.log('File can be read and written');
} catch (err) {
  console.error('No Read and Write access');
}
```

**输出:**

```js
Giving only read permission to user

> Checking Permission for reading the file
File can be read

> Checking Permission for reading and writing to file
No Read and Write access
```

**示例 2:** 此示例显示了文件存在时的测试。

```js
// Node.js program to demonstrate the
// fs.accessSync() method

// Import the filesystem module
const fs = require('fs');

// Test the if the file exists
console.log('\n> Checking if the file exists');
try {
  fs.accessSync('example.txt', fs.constants.F_OK);
  console.log('File does exist');
} catch (err) {
  console.error('File does not exist');
}

console.log('\nCreating the file');
fs.writeFileSync("example.txt", "Test File");

// Test the if the file exists again
console.log('\n> Checking if the file exists');
try {
  fs.accessSync('example.txt', fs.constants.F_OK);
  console.log('File does exist');
} catch (err) {
  console.error('File does not exist');
}
```

**输出:**

```js
> Checking if the file exists
File does not exist

Creating the file

> Checking if the file exists
File does exist
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ accesssync _ path _ mode](https://nodejs.org/api/fs.html#fs_fs_accesssync_path_mode)