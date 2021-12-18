# Node.js fsPromises.chmod()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromiss-chmod-method/](https://www.geeksforgeeks.org/node-js-fspromises-chmod-method/)

**fsPromises.chmod()** 方法用于更改给定路径的权限。这些权限可以使用对应于各自文件模式的字符串常量或八进制数来指定。

**注意:**Windows 平台只支持写权限的更改。它不支持区分用户、组或其他人的权限。它更改文件的权限，然后在成功时无参数地解析承诺。

**语法:**

```
fsPromises.chmod( path, mode)
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** It is a string, buffer or web address that indicates the path of the file whose permissions must be changed.
*   **mode:** is a string or octal integer constant, which indicates the permission to be granted. The logical or operator can be used to separate multiple permissions.

下面的例子说明了 Node.js 中的 fsPromises.chmod()方法:

**示例 1:** 该示例显示了使用八进制整数常量来授予文件权限。

```
// Node.js program to demonstrate the 
// fsPromises.chmod() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = require('fs').promises;

console.log("Granting only read access to user"); 

fsPromises.chmod("example.txt", 0o400 ) 

console.log("\nReading the file contents"); 

console.log(fs.readFileSync("example.txt", 'utf8')); 

console.log("\nTrying to write to file"); 

try { 
    fs.writeFileSync('example.txt', 
    "This file has now been edited."); 
} 
catch (e) { 
    console.log("Error Code:", e.code); 
} 

console.log("\nGranting read and write access to user"); 

fsPromises.chmod("example.txt", 0o600 ) 

console.log("Trying to write to file"); 

fs.writeFileSync('example.txt', 
    "This file has now been edited."); 

console.log("\nReading the file contents"); 
console.log(fs.readFileSync("example.txt", 'utf8')); 
```

**输出:**

```
Granting only read access to user

Reading the file contents     
This file has now been edited.

Trying to write to file       
Error Code: EPERM

Granting read and write access to user
Trying to write to file

Reading the file contents
This file has now been edited.

```

**示例 2:** 该示例显示了使用字符串常量和或运算符来赋予文件权限

```
// Node.js program to demonstrate the 
// fsPromises.chmod() method 

// Import the filesystem module 
const fs = require('fs'); 
const fsPromises = fs.promises;

// Grant only read permission to user 
console.log("Granting only read access to user"); 
fsPromises.chmod("example.txt", fs.constants.R_OK);

// Reading the file 
console.log("File Contents:", 
    fs.readFileSync("example.txt", 'utf8')); 

// Trying to write to file 
try { 
  console.log("\nTrying to write to file"); 
  fs.writeFileSync('example.txt', 
    "This file now has been edited."); 
} 
catch (e) { 
  console.log(
   "Error Occurred, Error Code:", e.code); 
} 

// Granting both read and 
// write permission 
console.log("\nGranting both read and "
        + 'write permission to user"); 
fsPromises.chmod("example.txt", 
   fs.constants.R_OK | fs.constants.W_OK);

// Check the file mode 
console.log("Current File Mode:", 
    fs.statSync("example.txt").mode); 

console.log("Trying to write to file"); 
try
{
  fs.writeFileSync('example.txt', 
    "This file now has been edited."); 
} catch (e) {
  console.log("Error ", e.code);
}

console.log("File Contents:", 
    fs.readFileSync("example.txt", 'utf8')); 
```

**输出:**

```
Granting only read access to user
File Contents: This file has now been edited.  

Trying to write to file
Error Occurred, Error Code: EPERM

Granting both read and write permission to user
Current File Mode: 33060
Trying to write to file
Error  EPERM
File Contents: This file has now been edited.

```

**参考:**[https://nodejs . org/API/fs . html # fs _ fspromises _ chmod _ path _ mode](https://nodejs.org/api/fs.html#fs_fspromises_chmod_path_mode)