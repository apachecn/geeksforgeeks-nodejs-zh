# Node.js fs.createWriteStream()方法

> 原文:[https://www . geesforgeks . org/node-js-fs-createwritestream-method/](https://www.geeksforgeeks.org/node-js-fs-createwritestream-method/)

**createWriteStream()方法** 是一个 fs 模块的内置应用编程接口，允许 快速生成一个可写流，用于将数据写入文件。当涉及到非常大的数据量时，与像 fs.writeFile 这样的方法相比，这种方法可能是更聪明的选择。

**语法:**

```
fs.createReadStream( path, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Path:** This parameter stores the file path of the read file. It can be a string, a buffer or a web address.
*   **option:** is an optional parameter for saving strings or objects.

**返回值:** 该方法返回 **fs。**读流对象。

以下示例说明了 Node.js 中的 **createWriteStream()方法**【T4:

**示例 1:** 本示例使用 fs.createWriteStream()方法将一些内容写入文件。

 <gfg-tab role="tab" slot="tab" id="gfg-tab-0"><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="javascript">```
// Node.js program to demonstrate the 
// fs.createWriteStream() method 

// Include fs module 
let fs = require('fs'), 

// Use fs.createWriteStream() method 
// to write the file 
let writer = fs.createWriteStream('test_gfg.txt') 

// Read and display the file data on console 
writer.write('GeeksforGeeks');
```</gfg-panel></gfg-tab>