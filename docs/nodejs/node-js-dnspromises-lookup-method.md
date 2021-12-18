# node . js dnspromses . lookup()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromies-lookup-method/](https://www.geeksforgeeks.org/node-js-dnspromises-lookup-method/)

**dnsPromises.lookup()方法**是 dns 模块 Promises 对象的内置应用编程接口，用于将给定参数的指定主机名的 IP 地址解析为第一个找到的 A (IPv4)或 AAAA (IPv6)记录。

**语法:**

```js
dnsPromises.lookup( hostname, options )
```

**参数:**该方法有两个参数，如上所述，如下所述:

1.  **Hostname:** This parameter specifies a string that represents the hostname to be checked.
2.  **Option:** It is an integer or the form of an object. It specifies the options to be used in the lookup process.
    *   **Family:** is the integer value of the specified record family. Its value must be between 4, 6 or 0, where 0 means to return both IPv4 and IPv6, 4 means to return IPv4 and 6 means to return IPv6\. The default value is 0.
    *   **Tip:** is a number that specifies one or more getaddrinfo flags. Multiple flags can be passed by bitwise OR of their values.
    *   **All:** It is a Boolean parameter. If set to true, the callback returns all the resolved addresses in the array; otherwise, it returns a single address. Its default value is FALSE.
    *   **is verbatim:** is a Boolean parameter. If set to true, the callback will get all the resolved IPv4 and IPv6 addresses, just as the DNS resolver returns out of order. If set to FALSE, the IPv4 address will be placed before the IPv6 address. The default value is false now, but it is expected to be true in the near future.

**返回值:**该方法返回错误、IP 地址族和 IP 地址。

下面的例子说明了在 Node.js 中使用 dnsPromises.lookup()方法:

**例 1:**

```js
// Node.js program to demonstrate the   
// dnsPromises.lookup() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.lookup() method
const options = {

    // Setting family as 6 i.e. IPv6
    family: 6,
    hints: dns.ADDRCONFIG | dns.V4MAPPED,
};

// Calling dnsPromises.lookup() for hostname
// geeksforgeeks.org
dnsPromises.lookup('geeksforgeeks.org', options).then((response) => {
  console.log(' family: IPv%s address: %j', response.family, response.address);
});
```

**输出:**

```js
 family: IPv6 address: "fd00:0:14:13::22da:3e74"

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dnsPromises.lookup() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.lookup()
// method, all as true
const options = {
    all:true,
};

dnsPromises.lookup('geeksforgeeks.org', options).then((response) => {
    console.log('addresses: %j', response);
});
```

**输出:**

```js
addresses: [{"address":"34.218.62.116", "family":4},
{"address":"fd00:0:14:13::22da:3e74", "family":6}]

```

**例 3:**

```js
// Node.js program to demonstrate the   
// dnsPromises.lookup() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Setting options for dnsPromises.lookup()
//  method, all as true
const options = {
    all:true,
};

// Asynchronous function 
(async function() {

    // Address from lookup function
    const addresses = await dnsPromises.lookup(
                    'geeksforgeeks.org', options);

    // Printing  addresses
    console.log("from async: ");
    console.log(addresses);   
})();
```

**输出:**

```js
from async:
[ { address: '34.218.62.116', family: 4 },
  { address: 'fd00:0:14:13::22da:3e74', family: 6 } ]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnspromies _ lookup _ hostname _ options](https://nodejs.org/api/dns.html#dns_dnspromises_lookup_hostname_options)