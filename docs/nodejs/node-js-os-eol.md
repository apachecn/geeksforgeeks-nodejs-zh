# Node.js os。eol〔t1〕

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-OS-eol/

**os。EOL 常量**是 os 模块的内置应用编程接口，用于获取操作系统指定的行尾字符或标记。

**语法:**

```js
os.EOL
```

**返回值:**返回运行它的操作系统指定的 EOL(行尾标记)。

下面的例子说明了**操作系统的使用。节点. js 中的 EOL 常数**:

**例 1:**

```js
// Node.js program to demonstrate the   
// os.EOL constants

// Allocating os module
const os = require('os');

// Printing os.EOL character(s) by
// stringifying to JSON otherwise it
// will simply print as end of line
console.log(JSON.stringify(os.EOL));
```

**输出:**

```js
"\r\n"

```

**例 2:**

```js
// Node.js program to demonstrate the   
// os.EOL constants

// Allocating os module
const os = require('os');

// Printing os.EOL character(s) with string
console.log("Paragraphs always contains EOL"
        + os.EOL + "EOL stands for end of line");

console.log("EOL varies from os to os" + os.EOL
            + "For windows it is \\r\\n" + os.EOL
            + "For POSIX it is \\n" + os.EOL);
```

**输出:**

```js
Paragraphs always contains EOL
EOL stands for end of line
EOL varies from os to os
For windows it is \r\n
For POSIX it is \n

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考资料:**[https://nodejs . org/API/OS . html # OS _ OS _ eol](https://nodejs.org/api/os.html#os_os_eol)