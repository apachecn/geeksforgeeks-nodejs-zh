# node . js crypto . creatediffeiehellmangroup()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-creatediffeiehellmangroup-method/](https://www.geeksforgeeks.org/node-js-crypto-creatediffiehellmangroup-method/)

**crypto . createDiffieHellmanGroup()方法**是用于创建 DiffieHellmangroup 的加密模块的内置应用程序编程接口。

**语法:**

```
crypto.createDiffieHellmanGroup( name )
```

**参数:**该方法接受单参数*名称*，类型为字符串。

**返回值:**返回 DiffieHellmanGroup。

以下示例说明了在 Node.js 中使用**crypto . createDiffieHellmangroup()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// crypto.createDiffieHellmanGroup()
// method

// Includes crypto module
const crypto = require('crypto');

// Defining name
const name = 'modp1';

// Creating DiffieHellman group
var diffHell = crypto.createDiffieHellmanGroup(name);

// Displays keys which are encoded
console.log(diffHell.generateKeys('hex'));
```

**输出:**

```
ace9c0ae947385ecd238d02e9e6431a8ceb7fd295c88271ba53e46026116d651898d498ea94980cc35a79e7254f02690a8e4b184cd0a7aecad97f77626741423f3b2f2eeb7b0de9a1fa35e22415ed1aae16860a9910528813dd852af5a36700b

```

**例 2:**

```
// Node.js program to demonstrate the     
// crypto.createDiffieHellmanGroup()
// method

// Includes crypto module
const crypto = require('crypto');

// Defining name by using mod15
// defined in in RFC 3526
const name = 'modp15';

// Creating DiffieHellman group
var diffHell = crypto.createDiffieHellmanGroup(name);

// Displays keys which are encoded
console.log(diffHell.generateKeys('base64'));
```

**输出:**

```
vkznZVRMdtS/3I9+cMfXQygigYhfbvo56xk5i3dYpsEnOFJVpcxzK4JEGChsO1cLHsbIKF1nS0hMuxzvfoMrOh6QyOT3Ptp/cmnGAwmRiKkOhpg6mWDUwMN1bxO+SQSUPAEWaRV8ub2wHb3dCxapGCGovuY+7AbrZO4DmIwYHULG01C3gQtLps74q/absa8orsOBW4Dcz/KNaw3njbBrHXnHOpyWiFYasgBz2YwQien8f9zeiAn1CjEbkfGysYdycqzfqBDuW19rDRDPINt1YJqrR5fpsbVjPJOmUNYKoTtk6VqEEx4y48j+f/z/qEOotjRDKJLAi4y7TmFCCfuetTVTn/b2PVGsKK+/rw2GYQZFOgZh/wYhk2UppKkrfBU2a0uBGU6Oo29N/BqgOU3pTZKCR+IXQdLOGJLYOjUo3VVsQbZi0WS9zt6YFwn3HtffkVYF/71lImA2RxZlrGgsPM7B/AytFqd0bVJ4h5ql0OKf/mvWdE2OPEhTRrpeWe5+

```

**参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ create diffuser group _ name](https://nodejs.org/api/crypto.html#crypto_crypto_creatediffiehellmangroup_name)