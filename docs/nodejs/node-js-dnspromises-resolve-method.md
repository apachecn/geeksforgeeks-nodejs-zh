# node . js dnspromses . resolve()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromses-resolve-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolve-method/)

**dnsPromises.resolve()方法**是 dns 模块 Promises 对象的内置应用程序编程接口，用于将主机名解析为资源记录数组。

**语法:**

```js
dnsPromises.resolve( hostname, rrtype )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **rrtype:** Specify the resource record type. Its default value is "a". The values are from a, AAAA, ANY, CNAME, MX, TXT, NS, NAPTR, PTR, SOA and SRV.
    *   **A:** IPv4 哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟
    *   **yyyy:t1】IPv6 哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟**
    *   **任意:**任意记录
    *   **cname:** Specification name record
    *   T28] MX: mail exchange record
    *   T32】NAPTR: name permission pointer record
    *   t36]ns

**返回值:**此方法返回错误，记录。

下面的例子说明了**方法在 Node.js 中的使用:**

**例 1:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Set the rrtype value for
// dnsPromises.resolve() method
const rrtype="NS";

// Calling dnsPromises.resolve() method 
dnsPromises.resolve('geeksforgeeks.org', rrtype).then((res) => {
    console.log(res);
});
```

**输出:**

```js
[ 'ns-869.awsdns-44.net',
  'ns-245.awsdns-30.com',
  'ns-1520.awsdns-62.org',
  'ns-1569.awsdns-04.co.uk' ]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Setting rrtype for dnsPromises.resolve() method
const rrtype = "MX";

// Calling dnsPromises.resolve() method asynchronously 
(async function() {

    // Records from resolve function
    const records = await dnsPromises.resolve('geeksforgeeks.org', rrtype);

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```js
from async:
[ { exchange: 'alt2.aspmx.l.google.com', priority: 5 },
  { exchange: 'aspmx.l.google.com', priority: 1 },
  { exchange: 'alt3.aspmx.l.google.com', priority: 10 },
  { exchange: 'alt4.aspmx.l.google.com', priority: 10 },
  { exchange: 'alt1.aspmx.l.google.com', priority: 5 } 
]

```

**例 3:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Set the rrtype for dnsPromises.resolve() method
const rrtype = "A";

// Calling dnsPromises.resolve() method 
dnsPromises.resolve('geeksforgeeks.org', rrtype).then((res) => {
    console.log(res);
});
```

**输出:**

```js
[ '34.218.62.116' ]

```

**例 4:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolve() method

// Accessing promises object from dns module
const dns = require('dns');

const dnsPromises = dns.promises;

// Set the rrtype for dnsPromises.resolve() method
const rrtype = "TXT";

// Calling dnsPromises.resolve() method 
dnsPromises.resolve('geeksforgeeks.org', rrtype).then((res) => {
    console.log(res);
});
```

**输出:**

```js
(node:12752) ExperimentalWarning: The dns.promises API is experimental
[ [ 'v=spf1 include:amazonses.com include:_spf.google.com -all' ],
  [ 'fob1m1abcdp777bf2ncvnjm08n' ] ]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnsprymes _ resolve _ hostname _ rrtype](https://nodejs.org/api/dns.html#dns_dnspromises_resolve_hostname_rrtype)