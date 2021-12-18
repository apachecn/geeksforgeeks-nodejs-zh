# Node.js fsPromises.rmdir()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-rmdir-method/](https://www.geeksforgeeks.org/node-js-fspromises-rmdir-method/)

**fsPromises.rmdir()** 方法用于删除给定路径的目录。它也可以递归地用于移除嵌套目录。它解决了承诺，成功后没有争论。

**语法:**

```js
fsPromises.rmdir( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** Save the directory path to be deleted. It can be a string, a buffer or a web address.
*   **Option:** is an object that can be used to specify optional parameters that affect operation. It has three optional parameters:
    *   **Recursion:** It is a Boolean value that specifies whether to perform recursive directory deletion. In this mode, if the specified path cannot be found and the operation is retried in case of failure, no error will be reported. The default value is false.
    *   **maxretries:** It is an integer value that specifies the number of times that Node.js will try to perform this operation if it fails due to any error. The operation is executed after the given retry delay. If the recursive option is not set to true, this option is ignored. The default value is 0.
    *   [T0】 retrydley: 【T1] It is an integer value that specifies the time (in milliseconds) to wait before retrying the operation. If the recursive option is not set to true, this option is ignored. The default value is 100ms.

下面的例子说明了 Node.js 中的**方法:**

***** 在机器路径中创建“gfg_directory”以正确运行代码。

**示例 1:** 本示例使用 fsPromises.rmdir()方法删除目录。

T4T6

```js
 // Node.js program to demonstrate the 
// fsPromises.rmdir() method 

// Import the filesystem module 
const fs = require('fs');
const fsPromises = require('fs').promises;

// Get the current filenames 
// in the directory 
getCurrentFilenames();

(async function main() {
    try {

        fsPromises.rmdir("gfg_directory")
        console.log("Folder Deleted!");

        // Get the current filenames 
        // in the directory to verify 
        getCurrentFilenames();

    } catch (err) {
        console.error(err);
    }
})();

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

T7