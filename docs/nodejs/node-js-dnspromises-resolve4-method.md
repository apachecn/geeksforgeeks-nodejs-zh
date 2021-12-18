# node . js dnspromses . resolve 4()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromses-resolve 4-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolve4-method/)

**dnsPromises.resolve4()方法**是 dns 模块承诺的内置应用程序编程接口，用于使用 DNS 协议解析指定主机名的 IPv4 地址(“A”记录)。

**语法:**

```
dnsPromises.resolve4( hostname, options )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string representing the hostname to be resolved.
*   **Option:** It is the form of an object.
    *   **ttl:** It is a Boolean parameter that specifies whether to retrieve the time-to-live value (TTL) of each record. If set to true, TTL (in seconds) of each record will be retrieved.

**返回值:**此方法返回错误，记录。

以下示例说明了在 Node.js 中使用**方法:**

**例 1:**

```
// Node.js program to demonstrate the   
// dnsPromises.resolve4() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolve4() method 
dnsPromises.resolve4('geeksforgeeks.org').then((res) => {
    console.log(res);
});

// Calling dnsPromises.resolve4() method 
// asynchronously 
(async function() {

    // Records from resolve function
    const records = await dnsPromises.resolve4(
                            'geeksforgeeks.org');
    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```
[ '34.218.62.116' ]
from async:
[ '34.218.62.116' ]

```

**例 2:**

```
// Node.js program to demonstrate the   
// dnsPromises.resolve4() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.resolve4() method
const options = {
    ttl:true,
};

// Calling dnsPromises.resolve4() method 
// asynchronously 
(async function() {

    // Records from resolve4 function
    const records = await dnsPromises.resolve4(
                    'geeksforgeeks.org', options);

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```
from async:
[ { address: '34.218.62.116', ttl: 30 } ]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnspromses _ resolve 4 _ hostname _ options](https://nodejs.org/api/dns.html#dns_dnspromises_resolve4_hostname_options)