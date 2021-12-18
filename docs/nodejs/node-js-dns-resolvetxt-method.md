# Node.js dns.resolveTxt()方法

> 原文:[https://www . geesforgeks . org/node-js-DNS-resolve text-method/](https://www.geeksforgeeks.org/node-js-dns-resolvetxt-method/)

**dns.resolveTxt()方法**是 dns 模块的内置应用编程接口，用于使用 dns 协议解析指定主机名的 Txt 或文本查询记录。

**语法:**

```js
dns.resolveTxt( hostname, callback )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Callback:** Specifies the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **Address:** It is a string array that represents the record of the returned text query host name.

**返回值:**此方法返回错误，通过回调函数寻址。这些数据作为参数传递给回调函数。

以下示例说明了在 Node.js 中 dns.resolveTxt()方法的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// dns.resolveTxt() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveTxt() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolveTxt('geeksforgeeks.org', (err, 
    addresses) => console.log('TXT records: %j', addresses));
```

**输出:**

```js
TXT records: [
    ["fob1m1abcdp777bf2ncvnjm08n"],
    ["v=spf1 include:amazonses.com include:_spf.google.com -all"]
]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dns.resolveTxt() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveTxt() method for
// hostname google.com and displaying
// them in console as a callback
dns.resolveTxt('google.com', (err, 
    addresses) => console.log('TXT records: %j', addresses));
```

**输出:**

```js
TXT records: [
    ["globalsign-smime-dv=CDYX+XFHUw2wml6/Gb8+59BsH31KzUr6c1l2BPvqKX8="],
    ["v=spf1 include:_spf.google.com ~all"],
    ["docusign=1b0a6754-49b1-4db5-8540-d2c12664b289"],
    ["facebook-domain-verification=22rm551cu4k0ab0bxsw536tlds4h95"],
    ["docusign=05958488-4752-4ef2-95eb-aa7ba8a3bd0e"]
]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolvetxt _ hostname _ callback](https://nodejs.org/api/dns.html#dns_dns_resolvetxt_hostname_callback)