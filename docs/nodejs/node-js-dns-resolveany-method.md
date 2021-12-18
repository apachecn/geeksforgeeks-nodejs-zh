# Node.js dns.resolveAny()方法

> 原文:[https://www . geesforgeks . org/node-js-DNS-resolve any-method/](https://www.geeksforgeeks.org/node-js-dns-resolveany-method/)

**dns.resolveAny()方法**是 dns 模块的内置应用编程接口，用于使用 dns 协议解析指定主机名的所有记录(即“Any”或“*”)。

**语法:**

```
dns.resolveAny( hostname, callback )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Callback:** Specifies the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **ret:** It is an object that represents the return record of the host name.

**返回值:**此方法返回错误，通过回调函数记录。这些数据作为参数传递给回调函数。

可以返回的记录有:

*   **A:** IPv4 地址
*   **AAAA:** IPv6 地址
*   **任意:**任意记录
*   **CNAME:** 典名记载
*   **MX:** 邮件交换记录
*   **NAPTR:** 名称权限指针记录
*   **NS:** 名称服务器记录
*   **PTR:** 指针记录
*   **SOA:** 权限记录的开始
*   **SRV:** 服务记录
*   **TXT:** 文字记录

下面的例子说明了在 Node.js 中 dns.resolveAny()方法的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveAny() method for 
// hostname geeksforgeeks.org and displaying
// them in console as a callback
dns.resolveAny('geeksforgeeks.org', (err, 
    ret) => console.log('records: %j', ret));
```

**输出:**

```
records: [
    {"value":"ns-1520.awsdns-62.org","type":"NS"},
    {"value":"ns-1569.awsdns-04.co.uk","type":"NS"},
    {"value":"ns-245.awsdns-30.com","type":"NS"},
    {"value":"ns-869.awsdns-44.net","type":"NS"}
]

```

**例 2:**

```
// Node.js program to demonstrate the   
// dns.resolveAny() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveAny() method for 
// hostname localhost and displaying
// them in console as a callback
dns.resolveAny('localhost', (err, 
    ret) => console.log('records: %j', ret));
```

**输出:**

```
records: [
    {"address":"127.0.0.1", "ttl":0, "type":"A"}
]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolveany _ hostname _ callback](https://nodejs.org/api/dns.html#dns_dns_resolveany_hostname_callback)