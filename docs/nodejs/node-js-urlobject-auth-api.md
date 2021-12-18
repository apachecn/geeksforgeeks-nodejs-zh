# Node.js urlObject.auth API

> 原文:[https://www.geeksforgeeks.org/node-js-urlobject-auth-api/](https://www.geeksforgeeks.org/node-js-urlobject-auth-api/)

借助 **urlObject.auth()** 方法，我们可以在主机名内找到认证参数。此方法返回参数字符串。

> **语法:urlObject.auth()**
> **返回:**返回身份验证参数的字符串。

**示例#1 :** 在本例中，借助 urlObject.auth()方法，我们能够从主机名中提取用户名和密码。

## java 描述语言

```
// importing the module 'url' 
const url = require('url');

var adr = 
'https://username=jitender:password=geeks@www.geeksforgeeks.com';

// Parse the address:
var q = url.parse(adr, true);

/* The parse method returns an object containing
 URL properties */
console.log(q.auth);
```

**输出:**

![](img/3f46cd53a2e7ec115117f02dd24d9633.png)

**例 2 :**

## java 描述语言

```
// importing the module 'url' 
const url = require('url');

var adr =
'https://username=author:password=truegeek@www.gfg.com';

// Parse the address:
var q = url.parse(adr, true);

/* The parse method returns an object containing
 URL properties */
console.log(q.search);
```

**输出:**

![](img/324b2992297f10fbe9ab402632203935.png)