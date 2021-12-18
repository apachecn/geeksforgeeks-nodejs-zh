# Node.js crypto.constants 属性

> 原文:[https://www . geesforgeks . org/node-js-crypto-constants-property/](https://www.geeksforgeeks.org/node-js-crypto-constants-property/)

**crypto.constants** 属性用于获取加密和安全相关操作的所有常用常量。这将返回包含加密常数的对象。

**语法:**

```
crypto.constants
```

**返回值:**该属性返回一个包含加密模块中常用常量的**对象**。

**示例:**本示例打印加密模块中使用的所有常用常量。

```
// Importing the crypto library
const crypto = require("crypto")

// Storing the constants inside the variable
let constants = crypto.constants

// Printing the constants
console.log(constants)
```