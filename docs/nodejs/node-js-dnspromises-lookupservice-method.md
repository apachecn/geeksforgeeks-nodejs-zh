# node . js dnspromses . lookup service()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromies-lookup service-method/](https://www.geeksforgeeks.org/node-js-dnspromises-lookupservice-method/)

**dnsPromises.lookupService()方法**是 dns 模块 Promises 对象的内置应用程序编程接口，用于使用操作系统的底层 getnameinfo 实现将地址和端口号解析为主机名和服务。

**语法:**

```
dnsPromises.lookupService( address, port )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Address:** It specifies a string representing the address to be resolved.
*   **Port:** It is a number that specifies the port number of the address whose service is to be resolved.

**返回值:**此方法返回错误、主机名和服务。

下面的例子说明了在 Node.js 中使用**方法:**

**例 1:**

```
// Node.js program to demonstrate the   
// dnsPromises.lookupService() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;

// Calling dnsPromises.lookupService() method
// for 127.0.0.1 port  number 22
dnsPromises.lookupService('127.0.0.1', 22).then((res) => {
    console.log(res.hostname, res.service);
});
```

**输出:**这里我电脑的名字是 my-lappy

```
my-lappy ssh
```

**例 2:**

```
// Node.js program to demonstrate the   
// dnsPromises.lookupService() method

// Accessing promises object from dns module
const dns = require('dns');
const dnsPromises = dns.promises;;

// Setting options for dnsPromises.lookup() method
const options = {

    // Setting family as 4 i.e. IPv4
    family: 4,
    hints: dns.ADDRCONFIG | dns.V4MAPPED,
};

dnsPromises.lookup('geeksforgeeks.org', options).then((response) => {
    if(response){
        console.log(response);

        // Calling dnsPromises.lookupService() method 
        dnsPromises.lookupService(response.address, 80).then((res) => {
            console.log(res.hostname, res.service);
        });
    }
});
```

**输出:**

```
{ address: '34.218.62.116', family: 4 }
ec2-34-218-62-116.us-west-2.compute.amazonaws.com 334

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnspromses _ lookupservice _ address _ port](https://nodejs.org/api/dns.html#dns_dnspromises_lookupservice_address_port)