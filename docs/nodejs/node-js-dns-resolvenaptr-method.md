# Node.js dns.resolveNaptr()方法

> 原文:[https://www . geesforgeks . org/node-js-DNS-resolvenaptr-method/](https://www.geeksforgeeks.org/node-js-dns-resolvenaptr-method/)

**dns.resolveNaptr()方法**是 dns 模块的内置应用程序编程接口，用于使用 dns 协议解析指定主机名的 Naptr 记录或基于正则表达式的记录。

**语法:**

```
dns.resolveNaptr( hostname, callback )
```

**参数:**该方法有两个参数，如上所述，如下所述:

*   **Hostname:** This parameter specifies a string that represents the hostname to be resolved.
*   **Callback:** Specifies the function to be called after DNS resolution of the host name.
    *   **Error:** The specified generation error.
    *   **Address:** is a string array that represents the returned host name record based on regular expression.

**返回值:**此方法通过回调函数返回错误或地址。这些数据作为参数传递给回调函数。参数地址将包含具有属性标志、服务、正则表达式、替换、顺序和首选项的对象数组。

以下示例说明了 dns.resolveNaptr()的使用；节点. js 中的方法:

**例 1:**

```
// Node.js program to demonstrate the   
// dns.resolveNaptr() method

// Accessing dns module
const dns = require('dns');

// Calling dns.resolveNaptr() method for
// hostname geeksforgeeks.org and displaying
// them in console as a callback
dns.resolveNaptr('geeksforgeeks.org', (err, 
    addresses) => console.log('naptr records: %j', addresses));
```

**输出:**

```
QueryReqWrap {
  bindingName: 'queryNaptr',
  callback: [Function],
  hostname: 'geeksforgeeks.org',
  oncomplete: [Function: onresolve],
  ttl: false,
  channel: ChannelWrap {} }
naptr records: undefined

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/API/DNS . html # DNS _ DNS _ resolvenaptr _ hostname _ callback](https://nodejs.org/api/dns.html#dns_dns_resolvenaptr_hostname_callback)