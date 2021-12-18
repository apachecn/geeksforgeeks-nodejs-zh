# Node.js dns.resolve4()方法

> 原文:[https://www.geeksforgeeks.org/node-js-dns-resolve4-method/](https://www.geeksforgeeks.org/node-js-dns-resolve4-method/)

**dns.resolve4()方法**是 dns 模块的内置应用程序编程接口，用于使用 dns 协议解析指定主机名的 IPv4 地址(“A”记录)。

**语法:**

```js
dns.resolve4( hostname, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Option:** It is the form of an object.
    *   **ttl:** It is a Boolean parameter that specifies whether to retrieve the time-to-live value (TTL) of each record. If set to true, TTL (in seconds) of each record will be retrieved.
*   **Callback:** Specify the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **Address:** is a string or object that represents the IPv4 address of the returned host name.

**返回值:**该方法通过回调函数返回错误、地址。这些数据作为参数传递给回调函数。

以下示例说明了在 Node.js 中 dns.resolve4()方法的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// dns.resolve4() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolve4() method for hostname
// geeksforgeeks.org and display them in
// console as a callback
dns.resolve4('geeksforgeeks.org', (err,
    address) => console.log('address: %j', address));
```

**输出:**

```js
address: ["34.218.62.116"]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dns.resolve4() method

// Accessing dns module
const dns = require('dns');

// Setting options value for
// dns.resolve4() method
const options = {
    ttl: true,
};

// Calling dns.resolve4() method for hostname
// geeksforgeeks.org and displaying them
// in console as a callback
dns.resolve4('geeksforgeeks.org', options, (err,
    address) => console.log('address: %j', address));
```

**输出:**

```js
address: [{"address":"34.218.62.116", "ttl":9}]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolve 4 _ hostname _ options _ callback](https://nodejs.org/api/dns.html#dns_dns_resolve4_hostname_options_callback)