# node . js dnspromses . getservers()方法

> 原文:[https://www . geesforgeks . org/node-js-dnspromses-get servers-method/](https://www.geeksforgeeks.org/node-js-dnspromises-getservers-method/)

**dnspromses . getservers()方法**是一个内置的 dns 模块应用编程接口，承诺对象，用于获取当前服务器的 IP 地址。

**语法:**

```js
dnsPromises.getServers()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法返回一个 RFC 5952 格式的 IP 地址数组，如当前主机的 DNS 解析中所配置的。如果使用自定义端口，则将附加一个字符串作为端口号。

以下示例说明了在 Node.js 中使用**方法:**

**例 1:**

```js
// Node.js program to demonstrate the   
// dnsPromises.getServers() method

// Accessing promises object from dns module
const { Resolver } = require('dns').promises;

// Calling Resolver constructor
const dnsPromises = new Resolver();

// Asynchronous function 
(async function() {

    // Address from getServers function
    const addresses = await dnsPromises.getServers();

    // Printing  addresses
    console.log(addresses);   
})();
```

**输出:**

```js
[ '10.15.13.139', '8.8.8.8' ]

```

**例 2:**

```js
// Node.js program to demonstrate the   
// dnsPromises.getServers() method

// Accessing promises object from dns module
const { Resolver } = require('dns').promises;

// Calling Resolver constructor
const dnsPromises = new Resolver();

// Asynchronous function 
(async function() {

    // Address from getServers function
    const addresses = await dnsPromises.getServers();

    // Printing each addresses
    addresses.forEach(element => {  
        console.log(element);  
    }); 
})();
```

**输出:**

```js
72.28.94.156
2306:2470:3160::8888
72.28.94.156:1053
[2306:2470:3160::8888]:1053

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ dnsprmisses _ getservers](https://nodejs.org/api/dns.html#dns_dnspromises_getservers)