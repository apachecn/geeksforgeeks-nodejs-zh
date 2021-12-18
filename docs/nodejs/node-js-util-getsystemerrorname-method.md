# node . js util . getsystemerrorname()方法

> 原文:[https://www . geesforgeks . org/node-js-util-getsystemerrorname-method/](https://www.geeksforgeeks.org/node-js-util-getsystemerrorname-method/)

**util.getSystemErrorName()方法**在 Node.js 标准库的 utilities 模块中定义。它用于了解程序中出现的错误类型。一般来说，这个方法在其他方法中使用，以了解该方法是否没有给出预期的响应，因为发生了一些错误，然后是什么类型的错误，以确保我们的程序确实会崩溃。

**语法**

```
util.getSystemErrorName( err )
```

**参数:**该方法接受一个参数“err”，该参数保存一个指定错误号或错误代码的数值。这个错误代码来自 Node.js API 本身。

**返回值:**返回字符串名称，即数字错误代码的错误名称。

**注意:**有一些常见系统错误被映射到特定的错误代码。系统错误和错误代码之间的映射依赖于平台。一些常见的系统错误如下所示。

*   **EACCES** (权限被拒绝):当文件试图访问其访问权限被禁止的文件时，会出现此错误。
*   **EADDRINUSE** (地址已在使用中):当试图将服务器(net、http 或 https)绑定到本地地址失败时，会出现这种情况，因为本地系统上的另一台服务器已经占用了该地址。
*   **经济重置**(对等方重置连接):当对等方强制关闭连接时，会出现这种情况。这通常是由于超时或重新启动导致远程套接字上的连接丢失。
*   **eidir**(是一个目录):当一个操作需要一个文件，但是给出了目录的路径名时，就会出现这种情况。
*   **EMFILE** (系统中打开的文件太多):当达到系统允许的最大文件描述符数量，并且至少关闭一个描述符后才能满足对另一个描述符的请求时，就会出现这种情况。并行同时打开多个文件时会遇到这种情况。
*   **ENOENT** (没有这样的文件或目录):当指定路径名的组件不存在，即给定路径找不到实体(文件或目录)时，fs 操作通常会引发此错误。
*   **ENOTDIR** (不是目录):当给定路径名的组件存在，但不是目录时，会出现这种情况。
*   **ENOTEMPTY** (目录不为空):当请求的目录不像预期的那样为空时，就会出现这种情况。
*   **TIMEDOUT** (操作超时):当建立连接并发送请求但由于被连接方在一段时间后没有正确响应而失败时，会出现这种情况。

**例 1:**

```
// Importing File System module
const fs = require('fs')

// Importing utilities module
const util = require('util')

fs.readdir('file/not/exist', (err, files) => {
  if(err){
    const errName = util.getSystemErrorName(err.errno)
    console.log(`Error Name --> ${errName}`)
    console.log(`Error Code --> ${err.errno}`)
  }else{
    for(let file in files){
      console.log(file)
    }
  } 
}) 
```

**输出:**

```
Error Name --> ENOENT
Error Code --> 4058

```

**说明:**程序基本上是取给定目录下的所有文件和文件夹。fs.readdir()方法获取目标目录的路径。在这种情况下，如果给定的路径无效，那么就会发生错误，这可能会破坏我们的程序，因此必须处理错误，并向用户提供一些有效的输出，以便用户知道为什么会发生错误。这里要处理的错误是使用 getSystemErrorName()方法，该方法返回发生的错误的名称。

**例 2:**

```
// Importing File System module
const fs = require('fs')

// Importing utilities module
const util = require('util')

fs.readdir('./index.js', (err, files) => {
  if(err){
    const errName = util.getSystemErrorName(err.errno)
    console.log(`Error Name --> ${errName}`)
    console.log(`Error Code --> ${err.errno}`)
  }else{
    for(let file in files){
      console.log(file)
    }
  } 
}) 
```

**输出:**

```
Error Name --> ENOTDIR
Error Code --> 4052

```

**说明:**程序基本上是取给定目录下的所有文件和文件夹。fs.readdir()方法获取目标目录的路径。由于给定的路径不是目录而是文件，因此会出现名为 ENOTDIR 的错误。