# 节点. js 流程.发布属性

> 原文:[https://www . geesforgeks . org/node-js-process-release-property/](https://www.geeksforgeeks.org/node-js-process-release-property/)

**process.release 属性**是流程模块的内置应用编程接口，用于获取 node.js.
当前发布的相关元数据**语法:**

```
process.release
```

**返回值:**该属性返回一个包含 nodejs 当前版本元数据的对象。该对象将包含名称、源 Url、头 Url、库 Url 和 lts 等属性。

*   **name:**name 的值在 Node.js 中始终为‘node’，对于旧版 io.js 版本，其值可以为‘io . js’。
*   **sourceUrl:** 它包含一个字符串，表示指向当前版本源代码为“. tar.gz”文件的绝对 Url。
*   **header Url:**它包含一个字符串，表示指向当前版本源头文件的绝对 URL 为“. tar.gz”文件。这个文件比源代码文件小，可以用来编译 Node.js 本机插件。
*   **libUrl:** 它包含一个表示绝对 Url 的字符串，指向与当前版本的架构和版本相匹配的‘node . lib’文件。该文件用于编译 Node.js 本机插件。此属性仅在 windows 版本中可用，在其他平台上可能会丢失。
*   **lts:** 表示最新稳定版本的字符串。它的价值可以是以下之一:
    *   **氩:**用于 4.x.x LTS 版本
    *   **硼:**适用于 6.x.x LTS 版本
    *   **碳元素:**适用于 8.x.x LTS 版本
    *   **Dubnium:** 适用于 10.x.x LTS 版本

以下示例说明了 **process.release 属性**在 Node.js 中的使用:
**示例 1:**

## java 描述语言

```
// Node.js program to demonstrate the     
// process.release Property

// Include process module
const process = require('process');

// Printing process.release property value
console.log(process.release);
```

**输出:**

```
{ name: 'node',
  lts: 'Dubnium',
  sourceUrl:
   'https://nodejs.org/download/release/v10.16.0/node-v10.16.0.tar.gz',
  headersUrl:
   'https://nodejs.org/download/release/v10.16.0/node-v10.16.0-headers.tar.gz',
  libUrl:
   'https://nodejs.org/download/release/v10.16.0/win-x64/node.lib' }
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the     
// process.release Property

// Include process module
const process = require('process');

// Printing process.release attribute count
var no_attr = 0;

// Calling process.release
var release = process.release;

// Iterating through all returned data
for (var key in release) {

  // Printing key and its releases
  console.log(key + ":\t\t\t" + release[key]);
  no_attr++;
}

// Printing count
console.log("Total no of attribute "
    + "available = " + no_attr);
```

**输出:**

```
name:          node
lts:           Dubnium
sourceUrl:     https://nodejs.org/download/release/v10.16.0/node-v10.16.0.tar.gz
headersUrl:    https://nodejs.org/download/release/v10.16.0/node-v10.16.0-headers.tar.gz
libUrl:        https://nodejs.org/download/release/v10.16.0/win-x64/node.lib
Total no of attribute available = 5
```

**例 3:**

## java 描述语言

```
// Node.js program to demonstrate the     
// process.release Property

// Include process module
const process = require('process');

// Calling process.release property
var release = process.release;

// Printing one data at a time
console.log("lts: " + release.lts);
console.log("source url: " + release.sourceUrl);
console.log("header url: " + release.headersUrl);
```

**输出:**

```
lts: Dubnium
source url: https://nodejs.org/download/release/v10.16.0/node-v10.16.0.tar.gz
header url: https://nodejs.org/download/release/v10.16.0/node-v10.16.0-headers.tar.gz
```

**注意:**以上程序将使用 node filename.js 命令编译运行。
T3【参考:T5【https://nodejs.org/api/process.html#process_process_release】T6