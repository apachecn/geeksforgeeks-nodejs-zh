# Node.js dns.resolve6()方法

> 原文:[https://www.geeksforgeeks.org/node-js-dns-resolve6-method/](https://www.geeksforgeeks.org/node-js-dns-resolve6-method/)

**dns.resolve6()方法**是 dns 模块的内置应用程序编程接口，用于使用 dns 协议解析指定主机名的 IPv6 地址(“AAAA”记录)。

**语法:**

```
dns.resolve6( hostname, options, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Option:** It is the form of an object.
    *   **ttl:** It is a Boolean parameter that specifies whether to retrieve the time-to-live value (TTL) of each record. If set to true, TTL (in seconds) of each record will be retrieved.
*   **Callback:** Specify the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **Address:** It is a string or object that represents the IPv6 address returned for the host name.

**返回值:**该方法通过回调函数返回 IPv6 地址。这些数据作为参数传递给回调函数。

下面的例子说明了 dns.resolve6()方法在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// dns.resolve6() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolve6() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolve6('geeksforgeeks.org', (err, 
    address) => console.log('address: %j', address));
```

**输出:**

```
address: ["fd00:0:14:13::22da:3e74"]

```

**例 2:**

```
// Node.js program to demonstrate the   
// dns.resolve6() method

// Accessing dns module
const dns = require('dns');

// Set the options for dns.resolve6() method
const options = {
    ttl : true
};

// Calling dns.resolve6() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolve6('geeksforgeeks.org', options, (err, 
    address) => console.log('address: %j', address));
```

**输出:**

```
address: [{"address":"fd00:0:14:13::22da:3e74", "ttl":30}]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolve 6 _ hostname _ options _ callback](https://nodejs.org/api/dns.html#dns_dns_resolve6_hostname_options_callback)