# Node.js scrypto.hkdf()函数

> 原文:[https://www . geesforgeks . org/node-js-scrypto-hkdf-function/](https://www.geeksforgeeks.org/node-js-scrypto-hkdf-function/)

**crypto.hkdf()** 是加密模块中加密类的内置应用编程接口，用于导出特定长度的密钥。

**语法:**

```js
const crypto.hkdf(digest, key, salt, info, keylen, callback)
```

**参数**:该函数以下列参数为参数。

*   **Abstract:** This is a series of summarization algorithms.
*   **Key:** It is the secret key.
*   **Salt:** It contains important value.
*   **Information:** contains additional information.
*   **keylen:** is the length of the key to be generated.
*   **Callback:** is for further operation.

**返回值**:该函数返回特定长度的派生键。

**例 1:**

index.js