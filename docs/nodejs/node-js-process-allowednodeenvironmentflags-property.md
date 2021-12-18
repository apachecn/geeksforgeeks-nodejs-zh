# node . js process . allowednodenvironmentflags 属性

> 原文:[https://www . geesforgeks . org/node-js-process-allownodenvironmentflags-property/](https://www.geeksforgeeks.org/node-js-process-allowednodeenvironmentflags-property/)

**process . allowednodenvironmentflags**是流程模块内 Process 类的内置应用编程接口，用于读取 NODE_OPTIONS 环境变量内允许的一组标志。

**语法:**

```
const process.allowedNodeEnvironmentFlags
```

**参数**:这个 api 不接受任何参数作为参数。

**返回值:**这个 api 返回一组 NODE_OPTIONS 环境变量内允许的标志。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// Process.allowedNodeEnvironmentFlags Property

// Importing process module
const process = require('process');

// Getting NodeEnvironmentFlags
const flags = process.allowedNodeEnvironmentFlags;

// Display the total size
console.log(flags.size)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
104
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// Process.allowedNodeEnvironmentFlags Property

// Importing process module
const process = require('process');

// Getting NodeEnvironmentFlags
process.allowedNodeEnvironmentFlags.forEach((flag) => {

    // Display the lenght for each
    console.log("Flag: ", flag, ", Length: ", flag.length)
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Flag:  --icu-data-dir , Length:  14
Flag:  --title , Length:  7
..
..

..

..
Flag:  --loader , Length:  8
Flag:  -r , Length:  2
```

**参考:**

[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ process _ allownodenvironmentflags](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_process_allowednodeenvironmentflags)