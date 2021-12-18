# Node.js fs.existsSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-existssync-method/](https://www.geeksforgeeks.org/node-js-fs-existssync-method/)

**fs.existsSync()方法**用于同步检查给定路径中是否已经存在文件。它返回一个布尔值，该值指示文件的存在。

**语法:**

```
fs.existsSync( path )
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **Path:** Save the path of the file to be checked. It can be a string, a buffer or a web address.

**返回值:**如果文件存在，则返回布尔值，即**真**，否则返回**假**。

下面的程序说明了 Node.js 中的 **fs.existsSync()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// fs.existsSync() method

// Import the filesystem module
const fs = require('fs');

// Get the current filenames
// in the directory
getCurrentFilenames();

let fileExists = fs.existsSync('hello.txt');
console.log("hello.txt exists:", fileExists);

fileExists = fs.existsSync('world.txt');
console.log("world.txt exists:", fileExists);

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("\nCurrent filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
  console.log("\n");
}
```

**输出:**

```
Current filenames:
hello.txt
index.js
package.json

hello.txt exists: true
world.txt exists: false
```

**例 2:**

```
// Node.js program to demonstrate the
// fs.existsSync() method

// Import the filesystem module
const fs = require('fs');

// Get the current filenames
// in the directory
getCurrentFilenames();

// Check if the file exists
let fileExists = fs.existsSync('hello.txt');
console.log("hello.txt exists:", fileExists);

// If the file does not exist
// create it
if (!fileExists) {
  console.log("Creating the file")
  fs.writeFileSync("hello.txt", "Hello World");
}

// Get the current filenames
// in the directory
getCurrentFilenames();

// Check if the file exists again
fileExists = fs.existsSync('hello.txt');
console.log("hello.txt exists:", fileExists);

// Function to get current filenames
// in directory
function getCurrentFilenames() {
  console.log("\nCurrent filenames:");
  fs.readdirSync(__dirname).forEach(file => {
    console.log(file);
  });
  console.log("\n");
}
```

**输出:**

```
Current filenames:
hello.txt
index.js
package.json

hello.txt exists: true

Current filenames:
hello.txt
index.js
package.json

hello.txt exists: true
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ exists sync _ path](https://nodejs.org/api/fs.html#fs_fs_existssync_path)