# 如何操作 Node.js 中带有承诺的基于回调的 fs.lstat()方法？

> 原文:[https://www . geesforgeks . org/操作方法-基于回调的-fs-lstat-带节点承诺的方法-js/](https://www.geeksforgeeks.org/how-to-operate-callback-based-fs-lstat-method-with-promises-in-node-js/)

**fs.lstat()** 方法是在 Node.js 的 File System 模块中定义的，File System 模块基本上就是和用户电脑的硬盘进行交互。lstat()方法使用在 stats 对象上定义的方法(lstat 提供的数据)给出了文件和文件夹的一些特定信息。
fs . lstat()方法基于回调。使用回调方法导致回调嵌套或回调地狱问题的可能性很大。因此为了避免这种情况，我们几乎总是喜欢使用基于承诺的方法。使用一些额外的 node.js 方法，我们可以用 promise 方式操作一个基于回调的方法。
**语法:**

```js
fs.lstat(path, options)
```

**注意:**不需要回调，因为我们是用承诺的方式操作的。
**参数:**该方法接受两个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或 url，用于指定目录的路径，我们尝试读取该目录的内容。
*   **选项:**为可选参数。一个选项参数是“bigint”，它是一个布尔值。这里我们指定 fs.lstat()返回的 stats 对象中的数值是否为 bigint(默认值-false)。

**返回值:**如果方法对承诺进行操作，则返回已解决或已拒绝的承诺。如果成功读取目录，则使用 stats 对象解析 Promise 否则，如果出现任何错误，则使用 error 对象拒绝 Promise(例如，指定的目录不存在或没有读取文件的权限等)。
从解析的承诺返回的 stats 对象中定义了一些属性和方法，这有助于获得一些关于目标文件或文件夹的具体细节。下面详细说明了一些方法。

*   **stats.isDirectory():** 如果 stats 对象描述文件系统目录，则返回 true。
*   **stats.isFile():** 如果 stats 对象描述了一个常规文件，则返回 true。
*   **stats.isSocket():** 如果 stats 对象描述了一个套接字，则返回 true。
*   **stats . issymbolilink():**如果 stats 对象描述了一个符号链接，则返回 true。
*   **stats.isFile():** 如果 stats 对象描述了一个常规文件，则返回 true。
*   **stats.isFIFO():** 如果 stats 对象描述了先进先出管道，则返回 true。
*   **stats.size:** 以字节为单位指定文件的大小。
*   **stats.blocks:** 它指定为文件分配的块数。

**示例 1:文件名:index.js**

## java 描述语言

```js
// Program to identify files and folders
// of a directory

// Importing File System and Utilities module
const fs = require('fs')
const util = require('util')

// Convert callback based methods to
// promise based methods
const readDir = util.promisify(fs.readdir)
const lStat = util.promisify(fs.lstat)

const fileOrFolder = async (path) => {
    const filenames = await readDir(path)

    for (let filename of filenames) {

        // Calling lstat method to give the
        // stats object for every directory
        const stats = await lStat(filename)

        // Check file or folder
        if (stats.isFile()) {
            console.log(
            `${filename} ---------> File`)
        } else {
            console.log(
            `${filename} ---------> Folder`)
        }
    }
}

// Driver code
// The process.cwd() gives current
// working directory
fileOrFolder(process.cwd())

    // If promise is rejected
    .catch(err => {
        console.log(`Error occurs,
        Error code -> ${err.code},
        Error No -> ${err.errno} `);
    });
```