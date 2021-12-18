# Node.js fs.access()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-access-method/](https://www.geeksforgeeks.org/node-js-fs-access-method/)

**fs.access()方法**用于测试给定文件或目录的权限。要检查的权限可以使用文件访问常数指定为参数。还可以通过使用按位“或”运算符创建一个具有多个文件常量的掩码来检查多个文件权限。
**注意:**不建议在调用 fs.open()、fs.readFile()或 fs.writeFile()之前使用 fs.access()方法检查文件的可访问性，因为它会引入争用情况，因为文件状态可能会在测试后被其他进程更改。

**语法:**

```js
fs.access( path, mode, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，表示必须测试权限的文件或目录的路径。
*   **模式:**是一个整数值，表示要测试的权限。逻辑或运算符可用于分隔多个权限。它可以有常量的值。这是一个可选参数。默认值为常量。
*   **回调:**这是一个在执行方法时会被调用的函数。
    *   **err:** 这是一个如果方法失败会抛出的错误。

以下示例说明了 Node.js 中的 **fs.access()方法**:
**示例 1:** 此示例显示了文件读写权限的测试。

## java 描述语言

```js
// Node.js program to demonstrate the
// fs.access() method

// Import the filesystem module
const fs = require('fs');

// Allowing only read permission
console.log("Giving only read permission to the user");
fs.chmodSync("example_file.txt", fs.constants.S_IRUSR);

// Test the read permission
fs.access('example_file.txt', fs.constants.R_OK, (err) => {
  console.log('\n> Checking Permission for reading the file');
  if (err)
    console.error('No Read access');
  else
    console.log('File can be read');
});

// Test both the read and write permissions
fs.access('example_file.txt', fs.constants.R_OK 
                  | fs.constants.W_OK, (err) => {
  console.log('\n> Checking Permission for reading"
                          + " and writing to file');
  if (err)
    console.error('No Read and Write access');
  else
    console.log('File can be read and written');
});
```