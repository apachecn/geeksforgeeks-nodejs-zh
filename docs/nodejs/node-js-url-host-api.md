# Node.js URL.host API

> 原文:[https://www.geeksforgeeks.org/node-js-url-host-api/](https://www.geeksforgeeks.org/node-js-url-host-api/)

**url.host** 是 **url** 模块内置的 **url** 类应用编程接口，用于获取和设置 URL 的主机部分。

**语法:**

```
const url.host
```

**返回值:**获取并设置 URL 的主机部分。
下面的程序说明了 **url.host** 方法的使用:
**示例 1:**

## java 描述语言

```
// node program to demonstrate the 
// url.host API as Setter 

//importing the module 'url'
const http = require('url');

// creating and initializing myURL
const myURL = new URL('https://example.com:80/foo#ram');

// Display href value of myURL before change
console.log("Before Change");
console.log(myURL.href);

// assigning host portion
// using host
console.log();
myURL.host = 'example.com:82';

// Display href value of myURL after change
console.log("After Change");
console.log(myURL.href);
```

**输出**:

```
Before Change
https://example.com:80/foo#ram

After Change
https://example.com:82/foo#ram
```

**例 2:**

## java 描述语言

```
// node program to demonstrate the 
// url.host API as Getter 

//importing the module 'url'
const http = require('url');

// creating and initializing myURL
const myURL = new URL('https://example.org:82/foo#ram');

// getting the host portion
// using host
const host = myURL.host;

// Display hash value 
console.log(host);
```

**输出:**

```
example.org:82
```

**注意**:以上程序将使用**节点 myapp.js** 命令编译运行。
**参考:**
[https://nodejs . org/dist/latest-v 10 . x/docs/API/URL . html # URL _ URL _ host](https://nodejs.org/dist/latest-v10.x/docs/api/url.html#url_url_host)