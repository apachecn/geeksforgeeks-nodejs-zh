# Node.js dns.lookupService()方法

> 原文:[https://www . geesforgeks . org/node-js-DNS-lookup service-method/](https://www.geeksforgeeks.org/node-js-dns-lookupservice-method/)

**dns.lookupService()方法**是 dns 模块的内置应用程序编程接口，用于使用操作系统的底层 getnameinfo 实现将地址和端口号解析为主机名。

**语法:**

```
dns.lookupService( address, port, callback )
```

**参数:**该方法有三个参数，如上所述，如下所述:

*   **Address:** It specifies a string representing the address to be resolved.
*   **Port:** It is a number that specifies the port number of the address whose service is to be resolved.
*   **Callback:** Specify the function to be called after the address and port are resolved.
    *   **Error:** The specified generation error.
    *   **Hostname:** String representation of the hostname. For example, geeksforgeeks.org
    *   **Service:** It is a string that specifies the name of the service. E.g. http

**返回值:**该方法通过回调函数返回错误、主机名和服务。这些数据作为参数传递给回调函数。

下面的例子说明了在 Node.js 中 **dns.lookupService()方法**的使用:

**示例 1:** 本地主机的 IP

```
// Accessing dns module
const dns = require('dns');

// Calling dns.lookupService() method for
// 127.0.0.1 port  number 22
dns.lookupService('127.0.0.1', 22,
         (err, hostname, service) => {

    // Printing hostname and service as callback
    console.log(hostname, service);
});
```

**输出:**这里我电脑的名字是 my-lappy

```
my-lappy ssh
```

**例 2:**

```
// Accessing dns module
const dns = require('dns');

// Setting options for dns.lookup() method
const options = {

    // Setting family as 4 i.e. IPv4
    family: 4,
    hints: dns.ADDRCONFIG | dns.V4MAPPED,
};

dns.lookup('www.geeksforgeeks.org', 
        options, (err, address, family) => {

    console.log('address:', address);
        if(err){
            console.log(err.stack);
        } else{

        // Calling dns.lookupService() method 
        dns.lookupService(address, 80,
                 (err, hostname, service) => {
            if(err){
                console.log(err.stack);
            }

            // Printing hostname and service
            // as callback
            console.log(hostname, service);
        });
    }
});
```

**输出:**

```
address: 42.106.162.241
42-106-162-241.live.vodafone.in http

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ lookupservice _ address _ port _ callback](https://nodejs.org/api/dns.html#dns_dns_lookupservice_address_port_callback)