# Node.js dns.resolveCname()方法

> 原文:[https://www . geesforgeks . org/node-js-DNS-resolve cname-method/](https://www.geeksforgeeks.org/node-js-dns-resolvecname-method/)

**dns.resolveCname()方法**是 dns 模块的内置应用程序编程接口，用于使用 dns 协议解析指定主机名的 Cname 记录。

**语法:**

```js
dns.resolveCname( hostname, callback )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Callback:** Specifies the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **Address:** It is a string array that represents the returned cname address of the host name.

**返回值:**这个方法通过回调函数返回错误、地址，这些数据作为参数传递给回调函数。

下面的例子说明了在 Node.js 中使用 dns.resolveCname()方法:

**例 1:**

```js
// Node.js program to demonstrate the   
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveCname() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolveCname('geeksforgeeks.org', (err, 
    addresses) => console.log('addresses: %j', addresses));
```

**输出:**

```js
QueryReqWrap {
  bindingName: 'queryCname',
  callback: [Function],
  hostname: 'geeksforgeeks.org',
  oncomplete: [Function: onresolve],
  ttl: false,
  channel: ChannelWrap {} }
addresses: undefined

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveCname() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolveCname('localhost', (err, 
    addresses) => console.log('addresses: %j', addresses));
```

**输出:**

```js
QueryReqWrap {
  bindingName: 'queryCname',
  callback: [Function],
  hostname: 'localhost',
  oncomplete: [Function: onresolve],
  ttl: false,
  channel: ChannelWrap {} }
addresses: undefined

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolvecname _ hostname _ callback](https://nodejs.org/api/dns.html#dns_dns_resolvecname_hostname_callback)