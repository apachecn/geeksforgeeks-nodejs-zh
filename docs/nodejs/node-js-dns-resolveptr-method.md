# Node.js dns.resolvePtr()方法

> 原文:[https://www . geesforgeks . org/node-js-DNS-resolveptr-method/](https://www.geeksforgeeks.org/node-js-dns-resolveptr-method/)

**dns.resolvePtr()方法**是 dns 模块的内置应用编程接口，用于使用 dns 协议解析指定主机名的 Ptr 或指针记录。

**语法:**

```js
dns.resolvePtr( hostname, callback )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Callback:** Specifies the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **Address:** is a string array, indicating the returned record of the host name pointer.

**返回值:**此方法返回错误，通过回调函数寻址。这些数据作为参数传递给回调函数。

以下示例说明了 dns.resolvePtr()的使用；节点. js 中的方法:

**例 1:**

```js
// Node.js program to demonstrate the   
// dns.resolvePtr() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolvePtr() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolvePtr('geeksforgeeks.org', (err, 
    addresses) => console.log('PTR records: %j', addresses));
```

**输出:**

```js
PTR records:[{"34.218.62.116"}]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dns.resolvePtr() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolvePtr() method for hostname
// google.com and displaying them in
// console as a callback
dns.resolvePtr('google.com', (err, 
    addresses) => console.log('PTR records: %j', addresses));
```

**输出:**

```js
PTR records:[{"172.217.164.142"}]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolveptr _ hostname _ callback](https://nodejs.org/api/dns.html#dns_dns_resolveptr_hostname_callback)