# node . js V8 . cacheddadaversiontag()方法

> 原文:[https://www . geeksforgeeks . org/node-js-V8-cacheddata versiontag-method/](https://www.geeksforgeeks.org/node-js-v8-cacheddataversiontag-method/)

**v8.cachedDataVersionTag()方法**是 v8 模块的内置应用编程接口，用于获取从 v8 版本派生的版本标签。

**语法:**

```
v8.cachedDataVersionTag();
```

**参数:**该方法没有任何参数。

**返回值:**该方法返回 v8 版本的版本标签、命令行标志和检测到的 CPU 特性。

下面的例子说明了 Node.js 中 v8.cachedDataVersionTag()方法的使用

**示例 1:** **文件名:index.js**

```
// Accessing v8 module
const v8 = require('v8');

// Calling v8.cachedDataVersionTag() 
tag = v8.cachedDataVersionTag();
console.log("cache data version tag is " + tag);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
cache data version tag is 4151506697
```

**示例 2:** **文件名:**

```
// Accessing v8 module
const v8 = require('v8');

// User defined function
function getTagVersion() {

    // Initializing with zero 
    var tagVersion = 0;

    // Calling v8.cachedDataVersionTag() 
    tagVersion = v8.cachedDataVersionTag();

    return tagVersion;
}

// Function call
var result = getTagVersion();

// Printing Tag version
console.log("The Cache Data Version is:", result);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
The Cache Data Version is: 1165837633
```

**参考:**[https://nodejs . org/API/V8 . html # V8 _ V8 _ cacheddataversion tag](https://nodejs.org/api/v8.html#v8_v8_cacheddataversiontag)