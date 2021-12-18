# node . js dnspromses . resolvesoa()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromses-resolve so a-method/](https://www.geeksforgeeks.org/node-js-dnspromises-resolvesoa-method/)

**dnsPromises.resolveSoa()方法**是 dns 模块 Promises 对象的内置应用程序编程接口，用于使用 DNS 协议解析指定主机名的 Soa 或权限记录的开始。

**语法:**

```
dnsPromises.resolveSoa( hostname )
```

**参数:**该方法有一个参数如上所述，描述如下:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.

**返回值:**这个方法返回错误，地址。地址参数将包含 nsname、hostmaster、serial、refresh、retry、expire 和 minttl 属性。

下面的例子说明了**方法在 Node.js 中的使用:**

**例 1:**

```
// Node.js program to demonstrate the   
// dnsPromises.resolveSoa() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveSoa() method 
dnsPromises.resolveSoa('google.com').then((res) => {
    console.log("for google : ");
    console.log(res);
});
```

**输出:**

```
for google :
{ nsname: 'ns1.google.com',
  hostmaster: 'dns-admin.google.com',
  serial: 290031082,
  refresh: 900,
  retry: 900,
  expire: 1800,
  minttl: 60
}

```

**例 2:**

```
// Node.js program to demonstrate the   
// dnsPromises.resolveSoa() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.resolveSoa() method 
// asynchronously 
(async function() {

    // Records from resolveSoa function
    const records = await dnsPromises.resolveSoa(
                    'geeksforgeeks.org');

    // Printing  records
    console.log("from async: ");
    console.log(records);   
})();
```

**输出:**

```
from async:
{ nsname: 'ns-869.awsdns-44.net',
  hostmaster: 'awsdns-hostmaster.amazon.com',
  serial: 1,
  refresh: 7200,
  retry: 900,
  expire: 1209600,
  minttl: 86400 
}

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnsprymes _ resolve SOA _ hostname](https://nodejs.org/api/dns.html#dns_dnspromises_resolvesoa_hostname)