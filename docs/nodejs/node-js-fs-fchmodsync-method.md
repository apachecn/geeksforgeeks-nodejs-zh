# Node.js fs.fchmodSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-fchmodsync-method/](https://www.geeksforgeeks.org/node-js-fs-fchmodsync-method/)

**fs.fchmodSync()方法**是 fs 模块的内置应用编程，用于同步更改给定文件描述符的权限。这些权限可以使用对应于各自文件模式的字符串常量或八进制数指定为参数。

**注意:**Windows 平台只支持写权限的更改。它也不支持区分用户、组或其他人的权限。

**语法:**

```
fs.fchmodSync( fd, mode )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **[FD:** is an integer that represents the file descriptor of the file whose permission needs to be changed.
*   **Mode:** Whether it is a string constant or an octal constant indicates the permission to be granted. The logical or operator can be used to separate multiple permissions.

下面的例子说明了 Node.js 中的 **fs.fchmodSync 方法**:

**示例 1:** 该示例显示了使用字符串常量和或运算符来授予文件权限。

```
// Node.js program to demonstrate the
// fs.fchmodSync method

// Import the filesystem module
const fs = require('fs');

// Getting the file descriptor
const fd = fs.openSync('example_file.txt', 'r');

// Allowing only read permission
console.log("Giving only read permission to user");
fs.fchmodSync(fd, fs.constants.S_IRUSR);

// Check the file mode
console.log("Current File Mode:",
    fs.statSync("example_file.txt").mode);

// Reading the file
console.log("File Contents:",
    fs.readFileSync("example_file.txt", 'utf8'));

// Trying to write to file
try {
  console.log("Trying to write to file");
  fs.writeFileSync('example_file.txt', "Hello");
}
catch (e) {
  console.log("Error Found, Code:", e.code);
}

// Allowing both read and write permission
console.log("\nGiving both read and write permission to user");
fs.fchmodSync(fd, fs.constants.S_IRUSR | fs.constants.S_IWUSR);

// Check the file mode
console.log("Current File Mode:",
    fs.statSync("example_file.txt").mode);

console.log("Trying to write to file");
fs.writeFileSync('example_file.txt', 
    "This file has been written over.");

console.log("File Contents:", 
    fs.readFileSync("example_file.txt", 'utf8'));
```

**输出:**

```
Giving only read permission to user
Current File Mode: 33024
File Contents: Hello World
Trying to write to file
Error Found, Code: EACCES

Giving both read and write permission to user
Current File Mode: 33152
Trying to write to file
File Contents: This file has been written over.

```

**示例 2:** 该示例显示了八进制常量的用法，以赋予文件权限。

```
// Node.js program to demonstrate the
// fs.fchmodSync method

// Import the filesystem module
const fs = require('fs');

// Getting the file descriptor
const fd = fs.openSync('example_file.txt', 'r');

// Allowing only read permission
console.log("Giving only read permission to everyone");
fs.fchmodSync(fd, 0o444);

// Check the file mode
console.log("Current File Mode:", 
    fs.statSync("example_file.txt").mode);

// Reading the file
console.log("File Contents:", 
    fs.readFileSync("example_file.txt", 'utf8'));

// Trying to write to file
try {
  console.log("Trying to write to file");
  fs.writeFileSync('example_file.txt', "Hello");
}
catch (e) {
  console.log("Error Found, Code:", e.code);
}

// Allowing both read and write permission
console.log("\nGiving both read and "
    + "write permission to everyone");
fs.fchmodSync(fd, 0o666);

// Check the file mode
console.log("Current File Mode:", 
    fs.statSync("example_file.txt").mode);

console.log("Trying to write to file");

fs.writeFileSync('example_file.txt', 
    "This file has been written over.");

console.log("File Contents:", 
    fs.readFileSync("example_file.txt", 'utf8'));
```

**输出:**

```
Giving only read permission to everyone
Current File Mode: 33060
File Contents: Hello World
Trying to write to file
Error Found, Code: EACCES

Giving both read and write permission to everyone
Current File Mode: 33206
Trying to write to file
File Contents: This file has been written over.
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ fchmodsync _ FD _ mode](https://nodejs.org/api/fs.html#fs_fs_fchmodsync_fd_mode)