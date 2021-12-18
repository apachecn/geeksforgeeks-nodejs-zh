# node . js dnspromses . reverse()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromies-reverse-method/](https://www.geeksforgeeks.org/node-js-dnspromises-reverse-method/)

**dnsPromises.reverse()方法**是 dns 模块 Promises 对象的内置应用编程接口，用于使用反向 DNS 查询解析指定 IP 地址的主机名。

**语法:**

```
dnsPromises.reverse(ip_address)
```

**参数:**该方法有一个参数如上所述，描述如下:

*   **ip _ address:** This parameter specifies the IP address (IPv4 or IPv6) to be resolved.

**返回值:**此方法返回错误，主机名。

下面的例子说明了**方法在 Node.js 中的使用:**

**例 1:**

```
// Node.js program to demonstrate the   
// dnsPromises.reverse() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.reverse() method 
dnsPromises.reverse('31.13.66.35').then((res) => {
    console.log(res);
});
```

**输出:**

```
[ 'edge-star-mini-shv-01-iad3.facebook.com' ]

```

**例 2:**

```
// Node.js program to demonstrate the   
// dnsPromises.reverse() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.reverse() method 
// asynchronously 
(async function() {

    // Records from reverse function
    const records = await dnsPromises.reverse(
                        '34.218.62.116');

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```
from async:
[ 'ec2-34-218-62-116.us-west-2.compute.amazonaws.com' ]

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnspromes _ reverse _ IP](https://nodejs.org/api/dns.html#dns_dnspromises_reverse_ip)