# node . js dnspromses . resolvens()方法

> 原文:[https://www . geeksforgeeks . org/node-js-dnspromses-resolvens-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolvens-method/)

**dnsPromises.resolveNs()方法**是 dns 模块 Promises 对象的内置应用编程接口，用于使用 DNs 协议解析指定主机名的 NS 或名称服务器记录。

**语法:**

```js
dnsPromises.resolveNs( hostname )
```

**参数:**该方法有一个参数如上所述，描述如下:

*   **Hostname:** This parameter specifies a string representing the hostname to be resolved.

**返回值:**这个方法返回错误，地址。

下面的例子说明了**方法在 Node.js 中的使用:**

**例 1:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolveNs() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveNs() method 
dnsPromises.resolveNs('google.com').then((res) => {
    console.log("for google : ");
    console.log(res);
});
```

**输出:**

```js
for google :
[ 'ns2.google.com',
  'ns3.google.com',
  'ns4.google.com',
  'ns1.google.com'
]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolveNs() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveNs() method 
// asynchronously 
(async function() {

    // Records from resolveNs function
    const records = await dnsPromises.resolveNs(
                    'geeksforgeeks.org');

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```js
from async:
[ 'ns-1520.awsdns-62.org',
  'ns-869.awsdns-44.net',
  'ns-245.awsdns-30.com',
  'ns-1569.awsdns-04.co.uk'
]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnspromses _ resolvens _ hostname](https://nodejs.org/api/dns.html#dns_dnspromises_resolvens_hostname)