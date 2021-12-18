# Node.js process.versions 属性

> 原文:[https://www . geesforgeks . org/node-js-process-versions-property/](https://www.geeksforgeeks.org/node-js-process-versions-property/)

**process.versions 属性**是流程模块的内置应用编程接口，用于获取 node.js 模块的版本及其依赖关系。

**语法:**

```js
process.versions
```

**返回值:**该属性返回一个包含 node.js 模块及其依赖项版本的对象。

下面的例子说明了在 Node.js 中 **process.versions 属性**的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// process.versions property

// Include process module
const process = require('process');

// Printing process.versions property value
console.log(process.versions);
```

**输出:**

```js
{ http_parser: '2.8.0',
  node: '10.16.0',
  v8: '6.8.275.32-node.52',
  uv: '1.28.0',
  zlib: '1.2.11',
  brotli: '1.0.7',
  ares: '1.15.0',
  modules: '64',
  nghttp2: '1.34.0',
  napi: '4',
  openssl: '1.1.1b',
  icu: '64.2',
  unicode: '12.1',
  cldr: '35.1',
  tz: '2019a' }

```

**例 2:**

```js
// Node.js program to demonstrate the    
// process.versions property

// Include process module
const process = require('process');

// Printing process.versions property value
// and variable count
var no_versions = 0;

// Calling process.versions property
var versions = process.versions;

// Itterating through all returned data
for (var key in versions) {

  // Printing key and its versions
  console.log(key + ":\t\t\t" + versions[key]);
  no_versions++;
}

// Printing count value
console.log("Total no of values available = " + no_versions);
```

**输出:**

```js
http_parser:            2.8.0
node:                   10.16.0
v8:                     6.8.275.32-node.52
uv:                     1.28.0
zlib:                   1.2.11
brotli:                 1.0.7
ares:                   1.15.0
modules:                64
nghttp2:                1.34.0
napi:                   4
openssl:                1.1.1b
icu:                    64.2
unicode:                12.1
cldr:                   35.1
tz:                     2019a
Total no of values available = 15

```

**例 3:**

```js
// Node.js program to demonstrate the    
// process.versions property

// Include process module
const process = require('process');

// Calling process.versions property
var versions = process.versions;

// Printing one at a time
console.log("node version: " + versions.node);
console.log("openssl version: " + versions.openssl);
console.log("module versions: " + versions.modules);
```

**输出:**

```js
node version: 10.16.0
openssl version: 1.1.1b
module versions: 64

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/process . html # process _ process _ versions](https://nodejs.org/api/process.html#process_process_versions)