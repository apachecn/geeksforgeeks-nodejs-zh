# Node.js fs.chmod()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-chmod-method/](https://www.geeksforgeeks.org/node-js-fs-chmod-method/)

**fs.chmod()方法**用于更改给定路径的权限。这些权限可以使用对应于各自文件模式的字符串常量或八进制数来指定。

**注意:**Windows 平台只支持写权限的更改。它也不支持区分用户、组或其他人的权限。

**语法:**

```js
fs.chmod( path, mode, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address that indicates the path of the file whose permissions must be changed.
*   **mode:** is a string or octal integer constant, which indicates the permission to be granted. The logical or operator can be used to separate multiple permissions.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the method fails, this error will be thrown.

下面的例子说明了 Node.js 中的 **fs.chmod()方法**:

**示例 1:** 该示例显示了使用八进制整数常量来授予文件权限。

```js
// Node.js program to demonstrate the
// fs.chmod() method

// Import the filesystem module
const fs = require('fs');

// Grant only read permission to user
console.log("Granting only read access to user");

fs.chmod("example.txt", 0o400, () => {
  console.log("\nReading the file contents");
  console.log(fs.readFileSync("example.txt", 'utf8'));

  console.log("\nTrying to write to file");
  try {
    fs.writeFileSync('example.txt', "This file has now been edited.");
  }
  catch (e) {
    console.log("Error Code:", e.code);
  }

  // Grant both read and write permission to user
  console.log("\nGranting read and write access to user");
  fs.chmod("example.txt", 0o600, () => {
    console.log("Trying to write to file");
    fs.writeFileSync('example.txt', "This file has now been edited.");

    console.log("\nReading the file contents");
    console.log(fs.readFileSync("example.txt", 'utf8'));
  });
});
```

**输出:**

```js
Granting only read access to user

Reading the file contents
This is an example text file.

Trying to write to file
Error Code: EACCES

Granting read and write access to user
Trying to write to file

Reading the file contents
This file has now been edited.

```

**示例 2:** 该示例显示了使用字符串常量和或运算符来授予文件权限。

```js
// Node.js program to demonstrate the
// fs.chmod() method

// Import the filesystem module
const fs = require('fs');

// Grant only read permission to user
console.log("Granting only read access to user");
fs.chmod("example.txt", fs.constants.S_IRUSR, () => {

  // Reading the file
  console.log("File Contents:", fs.readFileSync("example.txt", 'utf8'));

  // Trying to write to file
  try {
    console.log("\nTrying to write to file");
    fs.writeFileSync('example.txt', "This file now has been edited.");
  }
  catch (e) {
    console.log("Error Occurred, Error Code:", e.code);
  }

  // Granting both read and write permission
  console.log("\nGranting both read and write permission to user");
  fs.chmod("example.txt", fs.constants.S_IRUSR | fs.constants.S_IWUSR, () => {

    // Check the file mode
    console.log("Current File Mode:", fs.statSync("example.txt").mode);

    console.log("Trying to write to file");
    fs.writeFileSync('example.txt', "This file now has been edited.");

    console.log("File Contents:", fs.readFileSync("example.txt", 'utf8'));
  });
});
```

**输出:**

```js
Granting only read access to user
File Contents: This file now has been edited.

Trying to write to file
Error Occurred, Error Code: EACCES

Granting both read and write permission to user
Trying to write to file
File Contents: This file now has been edited.

```

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ chmod _ path _ mode _ callback