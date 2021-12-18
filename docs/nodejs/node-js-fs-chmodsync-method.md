# Node.js fs.chmodSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-chmodsync-method/](https://www.geeksforgeeks.org/node-js-fs-chmodsync-method/)

**fs.chmodSync()方法**用于同步更改给定路径的权限。这些权限可以使用对应于各自文件模式的字符串常量或八进制数来指定。
**注意:**Windows 平台只支持写权限的更改。它也不支持区分用户、组或其他人的权限。
**语法:**

```js
fs.chmodSync( path, mode )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，表示权限必须更改的文件的路径。
*   **模式:**是字符串或八进制整数常量，表示要授予的权限。逻辑或运算符可用于分隔多个权限。

以下示例说明了 Node.js 中的 **fs.chmodSync()方法**:
**示例 1:** 此示例显示了使用字符串常量和 OR 运算符来赋予文件权限。

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.chmodSync method

// Import the filesystem module
const fs = require('fs');

// Allowing only read permission
console.log("Giving only read permission to user");
fs.chmodSync("example.txt", fs.constants.S_IRUSR);

// Check the file mode
console.log("Current File Mode:", 
    fs.statSync("example.txt").mode);

// Reading the file
console.log("File Contents:", 
    fs.readFileSync("example.txt", 'utf8'));

// Trying to write to file
try {
  console.log("Trying to write to file");
  fs.writeFileSync('example.txt', "Hello");
}
catch (e) {
  console.log("Error Found, Code:", e.code);
}

// Allowing both read and write permission
console.log("\nGiving both read and write"
    + " permissions to user");

fs.chmodSync("example.txt",
    fs.constants.S_IRUSR | fs.constants.S_IWUSR);

// Check the file mode
console.log("Current File Mode:",
    fs.statSync("example.txt").mode);

console.log("Trying to write to file");
fs.writeFileSync('example.txt', "World");

console.log("File Contents:",
    fs.readFileSync("example.txt", 'utf8'));
```

**输出:**

```js
Giving only read permission to user
Current File Mode: 33024
File Contents: Hello
Trying to write to file
Error Found, Code: EACCES

Giving both read and write permissions to user
Current File Mode: 33152
Trying to write to file
File Contents: World
```

**示例 2:** 该示例显示了使用八进制整数常量来赋予文件权限。

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.chmodSync method

// Import the filesystem module
const fs = require('fs');

// Allowing only read permission
console.log("Giving only read permission to everyone");
fs.chmodSync("example.txt", 0o444);

// Check the file mode
console.log("Current File Mode:", 
    fs.statSync("example.txt").mode);

// Reading the file
console.log("File Contents:", 
    fs.readFileSync("example.txt", 'utf8'));

// Trying to write to file
try {
  console.log("Trying to write to file");
  fs.writeFileSync('example.txt', "Hello");
}
catch (e) {
  console.log("Error Found, Code:", e.code);
}

// Allowing both read and write permission
console.log("\nGiving both read and "
     + "write permission to everyone");
fs.chmodSync("example.txt", 0o666);

// Check the file mode
console.log("Current File Mode:", 
    fs.statSync("example.txt").mode);

console.log("Trying to write to file");
fs.writeFileSync('example.txt', "World");

console.log("File Contents:", 
    fs.readFileSync("example.txt", 'utf8'));
```

**输出:**

```js
Giving only read permission to everyone
Current File Mode: 33060
File Contents: Hello
Trying to write to file
Error Found, Code: EACCES

Giving both read and write permission to everyone
Current File Mode: 33206
Trying to write to file
File Contents: World
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ chmod sync _ path _ mode](https://nodejs.org/api/fs.html#fs_fs_chmodsync_path_mode)