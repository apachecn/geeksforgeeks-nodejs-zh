# 节点. js 流程.报表.目录属性

> 原文:[https://www . geesforgeks . org/node-js-process-report-directory-property/](https://www.geeksforgeeks.org/node-js-process-report-directory-property/)

**process.report.directory** 是流程模块内 process 类的内置应用编程接口，用于获取或设置编写报表的目录。

**语法:**

```
const process.report.directory
```

**参数:**该 api 不接受任何参数作为参数。

**返回值:**这个 api 返回写报告的目录。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Process.report.directory Property

// Importing process module
const process = require('process');

// Assigning the directory
process.report.directory = "GFG"

// Display the result
console.log(process.report.directory)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
GFG
```

**例 2:**

**文件名:index . js**

## 【JavaScript】

```
// Node.js program to demonstrate the  
// Process.report.directory Property

// Importing process module
const process = require('process');

const directory = process.report.directory;

// Display the result
if (directory.length == 0)
    console.log("No directory is assigned")
else
    console.log(directory)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
No file name is assigned
```

**参考:**[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ process _ report _ directory](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_report_directory)