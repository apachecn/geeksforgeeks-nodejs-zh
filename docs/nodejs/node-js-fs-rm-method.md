# Node.js fs.rm()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-rm-method/](https://www.geeksforgeeks.org/node-js-fs-rm-method/)

fs.rm()方法用于删除给定路径下的文件。它也可以递归地用来删除目录。

**语法:**

```
fs.rm( path, options, callback );
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Path:** Save the path of the file to be deleted. It can be a string, a buffer or a web address.
*   **Option:** is an object that can be used to specify the optional parameters that will affect the operation as follows:
    *   **force:** is a Boolean value. If the path does not exist, the exception will be ignored.
    *   **Recursion:** is a Boolean value that specifies whether to perform recursive directory deletion. In this mode, if the specified path cannot be found and the operation is retried in case of failure, no error will be reported. The default value is false.
*   **Callback:** is a function that will be called when the method is executed.
    *   **err:** If the operation fails, this error will be thrown.

下面的例子说明了 Node.js 中的 fs.rm()方法:

**示例 1:** 本示例使用 fs.rm()方法删除文件。

**文件名:index . js**

## 【JavaScript】

```
// Import necessary modules
let fs = require('fs');

// List files before deleting
getCurrentFilenames();

fs.rm('./dummy.txt', { recursive:true }, (err) => {
    if(err){
        // File deletion failed
        console.error(err.message);
        return;
    }
    console.log("File deleted successfully");

    // List files after deleting
    getCurrentFilenames();
})

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

File deleted successfully

Current filenames:
index.js
node_modules
package-lock.json
package.json
```

**示例 2:** 本示例使用带有递归参数的 fs.rm()方法删除目录。

**文件名:index . js**

## 【JavaScript】

```
// Import the filesystem module 
const fs = require('fs'); 

// List the files in current directory 
getCurrentFilenames(); 

// Trying to delete directory without the recursive parameter 
fs.rm("./build", { recursive: false }, (err) => { 
  if (err) { 
    console.error(err);
  } 
  else { 
    console.log("Non Recursive: Directory Deleted!"); 
  } 
}); 

// Using the recursive option to delete directory 
fs.rm("./build", { recursive: true }, (err) => { 
  if (err) { 
    console.error(err); 
  } 
  else { 
    console.log("Recursive: Directory Deleted!"); 

    // List files after delete 
    getCurrentFilenames(); 
  } 
}); 

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

SystemError [ERR_FS_EISDIR]: Path is a directory: rm returned EISDIR 
(is a directory) ./build
    at internal/fs/utils.js:688:23
    at FSReqCallback.oncomplete (fs.js:184:5) {
  code: 'ERR_FS_EISDIR',
  info: {
    code: 'EISDIR',
    message: 'is a directory',
    path: './build',
    syscall: 'rm',
    errno: 21
  },
  errno: [Getter/Setter: 21],
  syscall: [Getter/Setter: 'rm'],
  path: [Getter/Setter: './build']
}

Recursive: Directory Deleted!

Current filenames:
index.js
node_modules
package-lock.json
package.json
```

**参考:**[https://nodejs . org/API/fs . html # fs _ fs _ RM _ path _ options _ callback](https://nodejs.org/api/fs.html#fs_fs_rm_path_options_callback)