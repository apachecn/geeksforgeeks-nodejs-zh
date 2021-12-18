# Node.js dns.lookup()方法

> 原文:[https://www.geeksforgeeks.org/node-js-dns-lookup-method/](https://www.geeksforgeeks.org/node-js-dns-lookup-method/)

**dns.lookup()方法**是 dns 模块的内置应用程序编程接口，用于将给定参数的指定主机名的 IP 地址解析为第一个找到的 A (IPv4)或 AAAA (IPv6)记录。

**语法:**

```js
dns.lookup( hostname, options, callback )
```

**参数:**该方法有三个参数，如上所述，描述如下:

*   **主机名:**该参数指定一个字符串，表示要检查的主机名。
*   **选项:**是整数或对象的形式。它指定查找过程中要使用的选项。
    1.  **族:**是指定记录族的整数值。该值必须在 4、6 或 0 之间，其中 0 表示返回 IPv4 和 IPv6 值，4 表示返回 IPv4，6 表示返回 IPv6。其默认值为 0。
    2.  **提示:**是指定一个或多个 getaddrinfo 标志的数字。通过对它们的值进行按位“或”，可以传递多个标志。
    3.  **all:** 是布尔型参数。如果设置为真，则回调返回数组中所有解析的地址，否则返回单个地址。它的默认值是 FALSE。
    4.  **逐字:**是布尔参数。如果它的值被设置为真，那么回调将获取由 DNS 解析器无序返回的所有解析的 IPv4 和 IPv6 地址。如果设置为 FALSE，IPv4 地址将放在 IPv6 地址之前。默认值现在为假，但预计在不久的将来为真。
*   **callback:** It specifies a function to be called after DNS resolution of the hostnames is done.
    1.  **错误:**如果生成，则指定错误。例如，如果主机名不存在或查找失败，则设置“ENOTFOUND”。
    2.  **地址:**是 IPv4 和 IPv6 地址的字符串表示。
    3.  **族:**是指定记录族的整数值。该值必须在 4、6 或 0 之间，其中 0 表示它不是 IPv4 或 IPv6 地址。0 表示操作系统使用的名称解析服务中存在故障。

    **返回值:**该方法通过回调函数返回错误、IP 地址族和 IP 地址。这些数据作为参数传递给回调函数。

    下面的例子说明了 **dns.lookup()方法**在 Node.js 中的使用:

    **例 1:**

    ```js
    // Node.js program to demonstrate the 
    // dns.lookup() method 

    // Accessing dns module
    const dns = require('dns');

    // Setting options for dns.lookup() method
    const options = {

        // Setting family as 6 i.e. IPv6
        family: 6,
        hints: dns.ADDRCONFIG | dns.V4MAPPED,
    };

    // Calling dns.lookup() for hostname geeksforgeeks.org
    // and displaying them in console as a callback
    dns.lookup('geeksforgeeks.org', options, (err, address, family) =>
            console.log('address: %j family: IPv%s', address, family));
    ```

    **输出:**

    ```js
    address: "fd00:0:13:13::22da:3e74" family: IPv6

    ```

    **例 2:**

    ```js
    // Node.js program to demonstrate the 
    // dns.lookup() method 

    // Accessing dns module
    const dns = require('dns');

    // Setting options for dns.lookup()
    // method, all as true
    const options = {
        all:true,
    };

    // Calling dns.lookup() for hostname
    //  geeksforgeeks.org and displaying
    // them in console as a callback
    dns.lookup('geeksforgeeks.org', options, (err, addresses) =>
            console.log('addresses: %j', addresses));
    ```

    **输出:**

    ```js
    addresses: [
        {"address":"34.218.62.116","family":4},
        {"address":"fd00:0:13:13::22da:3e74","family":6}
    ]

    ```

    **注意:**以上程序使用`node index.js`命令编译运行。

    **参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ lookup _ hostname _ options _ callback](https://nodejs.org/api/dns.html#dns_dns_lookup_hostname_options_callback)