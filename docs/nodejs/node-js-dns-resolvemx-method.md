# Node.js dns.resolveMx()方法

> 原文:[https://www.geeksforgeeks.org/node-js-dns-resolvemx-method/](https://www.geeksforgeeks.org/node-js-dns-resolvemx-method/)

**dns.resolveMx()方法**是 dns 模块的内置应用编程接口，用于使用 dns 协议解析指定主机名的 Mx 或邮件交换记录。

**语法:**

```js
dns.resolveMx( hostname, callback )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Callback:** Specifies the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **Address:** It is a string array that represents the return mail exchange record of the host name.

**返回值:**此方法返回错误，通过回调函数寻址。这些数据作为参数传递给回调函数。

下面的例子说明了在 Node.js 中 dns.resolveMx()方法的使用:

**例 1:**

```js
// Node.js program to demonstrate the   
// dns.resolveMx() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveMx() method for hostname
// geeksforgeeks.org and displaying them in
// console as a callback
dns.resolveMx('geeksforgeeks.org', (err, 
    addresses) => console.log('mx records: %j', addresses));
```

**输出:**

```js
mx records: [
    {"exchange":"aspmx.l.google.com","priority":1},
    {"exchange":"alt3.aspmx.l.google.com","priority":10},
    {"exchange":"alt4.aspmx.l.google.com","priority":10},
    {"exchange":"alt1.aspmx.l.google.com","priority":5},
    {"exchange":"alt2.aspmx.l.google.com","priority":5}
]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dns.resolveMx() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveMx() method for
// hostname google.com and displaying
// them in console as a callback
dns.resolveMx('google.com', (err, 
    addresses) => console.log('mx records: %j', addresses));
```

**输出:**

```js
mx records: [
    {"exchange":"alt3.aspmx.l.google.com","priority":40},
    {"exchange":"aspmx.l.google.com","priority":10},
    {"exchange":"alt2.aspmx.l.google.com","priority":30},
    {"exchange":"alt1.aspmx.l.google.com","priority":20},
    {"exchange":"alt4.aspmx.l.google.com","priority":50}
]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolve MX _ hostname _ callback](https://nodejs.org/api/dns.html#dns_dns_resolvemx_hostname_callback)