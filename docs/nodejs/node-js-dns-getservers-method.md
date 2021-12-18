# Node.js dns.getServers()方法

> 原文:[https://www . geesforgeks . org/node-js-DNS-getservers-method/](https://www.geeksforgeeks.org/node-js-dns-getservers-method/)

**dns.getServers()方法**是 dns 模块内置的应用编程接口，用于获取当前服务器的 IP 地址。
**语法:**

```
dns.getServers()
```

**参数:**此方法不接受任何参数。
**返回:**该方法返回当前主机的 DNS 解析中配置的 RFC 5952 格式的 IP 地址数组。如果正在使用自定义端口，将附加一个字符串作为端口号。
以下示例说明了在 Node.js 中使用 dns.getServers()方法:
**示例 1:**

## java 描述语言

```
// Node.js program to demonstrate the   
// dns.resolveSoa() method

// Accessing dns module
const dns = require('dns');

// Reading IP address of the current host
// and printing it to the console
console.log(dns.getServers());
```

**输出:**

```
[ '2402:3a80:1103:a055::34', '192.168.43.1' ]
```

**例 2:**

## java 描述语言

```
// Node.js program to demonstrate the   
// dns.resolveSoa() method

// Accessing dns module
const dns = require('dns');

// Reading IP address of the current host
// and printing it to the console
res = dns.getServers();

res.forEach(element => { 
    console.log(element); 
});
```

**输出:**

```
72.28.94.156
2306:2470:3160::8888
72.28.94.156:1053
[2306:2470:3160::8888]:1053
```

**注意:**以上程序将使用 node index.js 命令编译运行。
T3【参考:T5【https://nodejs.org/api/dns.html#dns_dns_getservers】T6