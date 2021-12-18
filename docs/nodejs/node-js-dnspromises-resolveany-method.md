# node . js dnspromses . resolveany()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromses-resolve any-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolveany-method/)

**dnsPromises.resolveAny()方法**是 dns 模块 Promises 对象的内置应用编程接口，用于使用 DNS 协议解析指定主机名的所有记录(即“Any”或“*”)。

**语法:**

```
dnsPromises.resolveAny( hostname )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **主机名:**该参数指定一个字符串，该字符串表示要解析的主机名。

**返回:**此方法返回错误，记录。
可能归还的记录包括

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

下面的例子说明了在 Node.js 中使用 dnsPromises.resolveAny()方法:

**例 1:**

```
// Node.js program to demonstrate the   
// dnsPromises.resolveAny() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveAny() method 
dnsPromises.resolveAny('geeksforgeeks.org').then((res) => {
    console.log("for geeksforgeeks : ");
    console.log(res);
});

// Calling dnsPromises.resolveAny() method 
dnsPromises.resolveAny('localhost').then((res) => {
    console.log("for localhost : ");
    console.log(res);
});
```

**输出:**

```
for localhost :
[ { address: '127.0.0.1', ttl: 0, type: 'A' } ]
for geeksforgeeks :
[ { exchange: 'alt1.aspmx.l.google.com', priority: 5, type: 'MX' },
  { exchange: 'alt2.aspmx.l.google.com', priority: 5, type: 'MX' },
  { exchange: 'aspmx.l.google.com', priority: 1, type: 'MX' },
  { exchange: 'alt3.aspmx.l.google.com', priority: 10, type: 'MX' },
  { exchange: 'alt4.aspmx.l.google.com', priority: 10, type: 'MX' },
  { value: 'ns-1520.awsdns-62.org', type: 'NS' },
  { value: 'ns-1569.awsdns-04.co.uk', type: 'NS' },
  { value: 'ns-245.awsdns-30.com', type: 'NS' },
  { value: 'ns-869.awsdns-44.net', type: 'NS' },
  { entries:
     [ 'v=spf1 include:amazonses.com include:_spf.google.com -all' ],
    type: 'TXT' },
  { entries: [ 'fob1m1abcdp777bf2ncvnjm08n' ], type: 'TXT' },
  { nsname: 'ns-869.awsdns-44.net',
    hostmaster: 'awsdns-hostmaster.amazon.com',
    serial: 1,
    refresh: 7200,
    retry: 900,
    expire: 1209600,
    minttl: 86400,
    type: 'SOA' } ]

```

**例 2:**

```
// Node.js program to demonstrate the   
// dnsPromises.resolveAny() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveAny() method 
// asynchronously 
(async function() {

    // Records from resolveAny function
    const records = await dnsPromises.resolveAny('geeksforgeeks.org');

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```
from async:
[ { exchange: 'alt4.aspmx.l.google.com', priority: 10, type: 'MX' },
  { exchange: 'alt1.aspmx.l.google.com', priority: 5, type: 'MX' },
  { exchange: 'alt2.aspmx.l.google.com', priority: 5, type: 'MX' },
  { exchange: 'aspmx.l.google.com', priority: 1, type: 'MX' },
  { exchange: 'alt3.aspmx.l.google.com', priority: 10, type: 'MX' },
  { value: 'ns-869.awsdns-44.net', type: 'NS' },
  { value: 'ns-1520.awsdns-62.org', type: 'NS' },
  { value: 'ns-245.awsdns-30.com', type: 'NS' },
  { value: 'ns-1569.awsdns-04.co.uk', type: 'NS' },
  { entries:
     [ 'v=spf1 include:amazonses.com include:_spf.google.com -all' ],
    type: 'TXT' },
  { entries: [ 'fob1m1abcdp777bf2ncvnjm08n' ], type: 'TXT' },
  { nsname: 'ns-869.awsdns-44.net',
    hostmaster: 'awsdns-hostmaster.amazon.com',
    serial: 1,
    refresh: 7200,
    retry: 900,
    expire: 1209600,
    minttl: 86400,
    type: 'SOA' } ]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnsprymes _ resolve any _ hostname](https://nodejs.org/api/dns.html#dns_dnspromises_resolveany_hostname)