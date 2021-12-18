# node . js dnspromses . resolve 6()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromses-resolve 6-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolve6-method/)

**dnsPromises.resolve6()方法**是 dns 模块承诺的内置应用程序编程接口，用于使用 DNS 协议解析指定主机名的 IPv6 地址(“AAAA”记录)。

**语法:**

```js
dnsPromises.resolve6( hostname, options )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Option:** It is the form of an object.
    *   **ttl:** is a Boolean parameter that specifies whether to retrieve the time-to-live value (TTL) of each record. If set to true, TTL (in seconds) of each record will be retrieved.

**返回值:**此方法返回错误，记录。

以下示例说明了在 Node.js 中使用**方法:**

**例 1:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolve6() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolve6() method 
dnsPromises.resolve6('geeksforgeeks.org').then((res) => {
    console.log(res);
});

// Calling dnsPromises.resolve6() method 
// asynchronously 
(async function() {

    // Records from resolve6 function
    const records = await dnsPromises.resolve6('geeksforgeeks.org');

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```js
from async:
[ 'fd00:0:13:13::22da:3e74' ]
[ 'fd00:0:13:13::22da:3e74' ]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dnsPromises.resolve6() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.resolve6() method
const options={
    ttl:true,
};

// Calling dnsPromises.resolve6() method 
// asynchronously 
(async function() {

    // Records from resolve6 function
    const records = await dnsPromises.resolve6(
                    'geeksforgeeks.org', options);

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```js
from async:
[ { address: 'fd00:0:13:13::22da:3e74', ttl: 30 } ]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnspromies _ resolve 6 _ hostname _ options](https://nodejs.org/api/dns.html#dns_dnspromises_resolve6_hostname_options)