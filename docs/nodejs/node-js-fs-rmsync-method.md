# Node.js fs.rmSync()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-rmsync-method/](https://www.geeksforgeeks.org/node-js-fs-rmsync-method/)

fs.rmSync()方法用于同步删除给定路径上的文件。它也可以通过配置 options 对象递归地用于移除目录。它返回未定义。

**语法:**

```
fs.rmSync( path, options );
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** Save the path of the file to be deleted. It can be a string, a buffer or a web address.
*   **Option:** is an object that can be used to specify the optional parameters that will affect the operation as follows:
    *   **force:** is a Boolean value. If the path does not exist, the exception will be ignored.
    *   **Recursion:** is a Boolean value that specifies whether to perform recursive directory deletion. In this mode, if the specified path cannot be found and the operation is retried in case of failure, no error will be reported. The default value is false.

下面的例子说明了 Node.js 中的 fs.rmSync()方法:

**示例 1:** 本示例使用 fs.rmSync()方法删除文件。

**文件名:index . js**

## 【JavaScript】

```
// Import necessary modules
let fs = require('fs');

// List files before deleting
getCurrentFilenames();

fs.rmSync('./dummy.txt');

// List files after deleting
getCurrentFilenames();

// This will list all files in current directory
function getCurrentFilenames() { 
    console.log("\nCurrent filenames:"); 
    fs.readdirSync(__dirname).forEach(file => { 
        console.log(file); 
    }); 
    console.log(""); 
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Current filenames:
dummy.txt
index.js
node_modules
package-lock.json
package.json

Current filenames:
index.js
node_modules
package-lock.json
package.json
```

**示例 2:** 本示例使用带有递归参数的 fs.rmSync()方法删除目录。

**文件名:index . js**

## 【JavaScript】

```
// Import the filesystem module 
const fs = require('fs'); 

// List the files in current directory 
getCurrentFilenames(); 

// Using the recursive option to delete directory 
fs.rmSync("./build", { recursive: true });

// List files after delete 
getCurrentFilenames(); 

// List all files in current directory
function getCurrentFilenames() { 
  console.log("\nCurrent filenames:"); 
  fs.readdirSync(__dirname).forEach(file => { 
    console.log(file); 
  }); 
  console.log("\n"); 
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Current filenames:
build
index.js
node_modules     
package-lock.json
package.json

Current filenames:
index.js
node_modules
package-lock.json
package.json
```

**参考:**T2】https://nodejs.org/api/fs.html#fs_fs_rmsync_path_options