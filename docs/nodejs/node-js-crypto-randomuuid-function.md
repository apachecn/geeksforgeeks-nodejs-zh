# Node.js crypto.randomUUID()函数

> 原文:[https://www . geesforgeks . org/node-js-crypto-randomuuid-function/](https://www.geeksforgeeks.org/node-js-crypto-randomuuid-function/)

**crypto.randomUUID()** 是加密模块中加密类的内置应用程序编程接口，用于生成随机的 RFC 4122 版本 4 UUID。

**语法:**

```
const crypto.randomUUID([options])
```

**参数:**该功能以**disablentracycache**为参数

**返回值:**这个函数返回一个随机的 RFC 4122 版本 4 UUID。

**例 1:**

## index.js

```
<script>
  // Node.js program to demonstrate the  
  // crypto.randomUUID() api

  // Importing crypto module
  const crypto = require('crypto')

  // getting a random RFC 4122 Version 4 UUID
  // by using randomUUID() method
  const val = crypto.randomUUID({disableEntropyCache : true});

  // display the result
  console.log("RFC 4122 Version 4 UUID : " + val)
</script>
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
RFC 4122 Version 4 UUID : 88368f2a-d5db-47d8-a05f-534fab0a0045
```

**例 2:**

## index . js

```
<script>
  // Node.js program to demonstrate the  
  // crypto.randomUUID() api

  // Importing crypto module
  const crypto = require('crypto')

  // getting a random RFC 4122 Version 4 UUID
  // by using randomUUID() method
  console.log(crypto.randomUUID())
</script>
```

使用以下命令运行 index.js 文件。

```
node index.js
```

**输出:**

```
e2d3286f-2d8f-471a-bacb-1e5d28d8727e
```

**参考**:[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ crypto _ randomuuid _ options](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_crypto_randomuuid_options)