# Node.js fsPromises.chown()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromises-chown-method/](https://www.geeksforgeeks.org/node-js-fspromises-chown-method/)

方法 用于更改文件的所有权，然后成功后无需任何争论即可解决 *承诺* 。 该功能接受用户 id 和组 id，可用于设置各自的所有者和组。

**语法:**

```
fsPromises.chown( path, uid, gid)

```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **路径:**它是一个字符串、缓冲区或网址，表示所有者和组必须更改的文件的路径。
*   **uid:** 是表示与要设置的所有者对应的用户 id 的整数。
*   **gid:** 是表示与要设置的组对应的组 id 的整数。

## java 描述语言

```
// Node.js program to demonstrate the 
// fsPromises.chown() method 

// Import the filesystem module 
const fs = require('fs'); 

let filepath = "example_file.txt"; 

// Set the owner to a new one keeping the group same 
// New owner is "GeeksforGeeks" with user id 4567
fsPromises.chown(filepath, 4567, 999 => { 
    console.log("uid and gid set successfully."); 
}); 
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 May 26 04:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 May 26 04:08 index.js

```

**代码输出:**

```
Given uid and gid set successfully
.

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 geeksforgeeks xubuntu 4 May 26 04:08 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 May 26 04:08 index.js

```

**例 2:** 本例展示了组的设置。

## java 描述语言

```
// Node.js program to demonstrate the 
// fsPromises.chown() method 

// Import the filesystem module 
const fs = require('fs'); 

let filepath = "example_file.txt"; 

// Set the owner and group both to a new one 
// New owner is "nitin" with owner id 8900 
// New group is "author" with group id 1024 
fsPromises.chown(filepath, 8900, 1024 => { 

console.log("uid and gid set successfully!"); 

}); 
```

**运行代码前:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 xubuntu xubuntu 4 May 26 04:19 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 May 26 04:19 index.js

```

**代码输出:**

```
Given uid and gid set successfully!

```

**运行代码后:**

```
xubuntu@xubuntu: ~/Desktop/fs-chown$ ls -l
total 8
-rw-rw--w- 1 nitin author 4 May 26 04:19 example_file.txt
-rw-rw-r-- 1 xubuntu xubuntu 290 May 26 04:19 index.js

```