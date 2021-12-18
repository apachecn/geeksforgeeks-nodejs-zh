# Node.js | os.version()方法

> 原文:[https://www.geeksforgeeks.org/node-js-os-version-method/](https://www.geeksforgeeks.org/node-js-os-version-method/)

**os.version()方法**用于识别操作系统内核的版本。该信息通过在 POSIX 系统上调用`uname`并在 Windows 系统上调用`RtlGetVersion()`或`GetVersionExW()`来确定。

**语法:**

```js
os.version()
```

**参数:**此功能不接受任何参数。

**返回值:**返回标识内核版本的字符串。

下面的程序说明了 Node.js 中的 **os.version()方法**:

**例 1:** 在 POSIX

```js
// Import the os module
const os = require("os");

let osVersion = os.version();
console.log("OS Version:", osVersion);
```

上

**输出:**

```js
OS Version: #24~18.04.1-Ubuntu SMP Mon Jul 28 16:12:28 UTC 2019
```

**示例 2:** 在 Windows 上

```js
// Import the os module
const os = require("os");

let osVersion = os.version();
console.log("OS Version:", osVersion);
```

**输出:**

```js
OS Version: Windows 10 Enterprise
```

**参考:**[https://nodejs . org/API/OS . html # OS _ OS _ version](https://nodejs.org/api/os.html#os_os_version)