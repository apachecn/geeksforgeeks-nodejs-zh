# Node.js fs-extra emptyDirSync()函数

> 原文:[https://www . geesforgeks . org/node-js-fs-extra-emptydirsync-function/](https://www.geeksforgeeks.org/node-js-fs-extra-emptydirsync-function/)

**emptyDirSync()** 功能是 [emptyDir()](https://www.geeksforgeeks.org/nodejs-fs-extra-emptydir-function/) 功能的同步版本。该函数确保给定的目录为空。如果目录不为空，它将删除该目录中的所有内容。目录本身不会被删除。如果目录不存在，它将由函数本身创建。

**语法:**

```js
fs.emptyDirSync(dir)
// OR
fs.emptydirSync(dir)
```

**参数:**该函数接受以下参数:

*   **dir:** 是包含目录路径的字符串。

**返回值:**函数不返回任何内容。

**按照步骤实现功能:**

**步骤 1:** 可以使用以下命令安装模块:

```js
npm install fs-extra
```

**步骤 2:** 安装模块后，您可以使用以下命令检查已安装模块的版本:

```js
npm ls fs-extra
```

![](img/7f250622aa2125b46b0e33ba7e88633d.png)

**步骤 3:** 使用以下命令创建一个名为 *index.js* 的文件，并在文件中要求 **fs-extra** 模块:

```js
const fs = require('fs-extra');
```

**步骤 4:** 要运行文件，在终端中写入以下命令:

```js
node index.js
```

**项目结构:**项目结构会是这样的。

![](img/5a04b4a9423b0180bdb62b253dc661e9.png)

**例 1:**

文件名:index.js

## java 描述语言

```js
// Requiring module
const fs = require("fs-extra");

// Function to calculate number of files in directory
const numberOfFiles = (dir) => {
  const noOfFiles = fs.readdirSync(dir);
  return noOfFiles.length;
};

// Directory  path
// This directory have 2 files in it
const dir = "dir";

// Number of files before calling the function
const before = numberOfFiles(dir);
console.log(
  `Number of files in directory before calling the function: ${before}`
);

// Function call
fs.emptyDirSync(dir);

// Number of files after calling the function
const after = numberOfFiles(dir);
console.log(`Number of files in directory after`+
            ` calling the function: ${after}`);
console.log("Directory is empty now");
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Number of files in directory before calling the function: 2
Number of files in directory after calling the function: 0
Directory is empty now
```

**例 2:**

文件名:index.js

## java 描述语言

```js
// Requiring module
const fs = require("fs-extra");

// Function to calculate number of files in directory
const numberOfFiles = (dir) => {
  const noOfFiles = fs.readdirSync(dir);
  return noOfFiles.length;
};

// Directory path
// This directory has only 1 file
const dir = "dir/direc";

// Number of files before calling the function
const before = numberOfFiles(dir);
console.log(
  `Number of files in directory before calling the function: ${before}`
);

// Function call
fs.emptyDirSync(dir);

// Number of files after calling the function
const after = numberOfFiles(dir);
console.log(`Number of files in directory after`+
            ` calling the function: ${after}`);
console.log("Directory is empty now");
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Number of files in directory before calling the function: 1
Number of files in directory after calling the function: 0
Directory is empty now
```

**参考:**[https://github . com/jprichardson/node-fs-extra/blob/HEAD/docs/emptyDir-sync . MD](https://github.com/jprichardson/node-fs-extra/blob/HEAD/docs/emptyDir-sync.md)