# Node.js URL.protocol API

> 原文:[https://www.geeksforgeeks.org/node-js-url-protocol-api/](https://www.geeksforgeeks.org/node-js-url-protocol-api/)

**url.protocol** 是 **url** 模块中 **url** 类的内置应用编程接口，用于获取和设置 URL 的协议部分。当使用特殊协议之一解析 URL 时，url.protocol 属性可以更改为另一个特殊协议，但不能更改为非特殊协议，反之亦然。

**语法:**

```js
const url.protocol
```

**返回值:**返回 URL 的协议部分。

下面的例子说明了 **url.protocol** 方法在 Node.js 中的使用:

**例 1:**

## java 描述语言

```js
// Node program to demonstrate the 
// url.protocol API as Setter 

// Importing the module 'url'
const http = require('url');

// Creating and initializing myURL
const myURL = new URL('https://geeksforgeeks.org:80/foo#ram');

// Display href value of myURL before change
console.log("Before Change");
console.log(myURL.href);

// Assigning protocol portion
// using protocol
console.log();
myURL.protocol = 'http';

// Display href value of myURL after change
console.log("After Change");
console.log(myURL.href);
```

**输出**:

```js
Before Change
https://geeksforgeeks.org:80/foo#ram

After Change
http://geeksforgeeks.org/foo#ram
```

**示例 2:** 本示例将特殊协议更改为非特殊协议。

## java 描述语言

```js
// Node program to demonstrate the 
// url.protocol API as Setter 

// Importing the module 'url'
const http = require('url');

// Creating and initializing myURL
const myURL = new URL('https://geeksforgeeks.org:80/foo#ram');

// Display href value of myURL before change
console.log("Before Change");
console.log(myURL.href);

// Assigning protocol portion
// with non special protocol 
// using protocol
console.log();
myURL.protocol = 'xyz';

// Display href value of myURL after change
console.log("After Change");
console.log(myURL.href);
```

**输出**:

```js
Before Change
https://geeksforgeeks.org:80/foo#ram

After Change
https://geeksforgeeks.org:80/foo#ram
```

**例 3:**

## java 描述语言

```js
// Node program to demonstrate the 
// url.protocol API as Getter 

// Importing the module 'url'
const http = require('url');

// Creating and initializing myURL
const myURL = new URL('https://geeksforgeeks.org:80/foo#ram');

// Getting the protocol portion
// using protocol
const protocol = myURL.protocol;

// Display hash value 
console.log("Protocol of current url is : " + protocol);
```

**输出:**

```js
Protocol of current url is : https:
```

**注意:**以上程序将使用**节点 myapp.js** 命令编译运行。
**参考:**[https://nodejs.org/api/url.html#url_url_protocol](https://nodejs.org/api/url.html#url_url_protocol)T9】