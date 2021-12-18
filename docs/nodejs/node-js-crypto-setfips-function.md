# Node.js crypto.setFips()函数

> 原文:[https://www . geesforgeks . org/node-js-crypto-setfips-function/](https://www.geeksforgeeks.org/node-js-crypto-setfips-function/)

**crypto.setFips()** 方法是加密模块中加密类的内置应用程序编程接口，用于在启用 Fips 的 Node.js 版本中启用符合 FIPS 的加密提供程序。

**语法:**

```
const crypto.setFips(bool)
```

**参数:**该 API 将布尔值作为参数。

**返回值**:这个 API 不返回任何东西。

**例 1:**

## index . js

```
// Node.js program to demonstrate the  
// crypto.setFips() method

// Importing crypto module
const crypto = require('crypto')

// Checking for error
try {

    // Enabling the FIPS compliant 
    // crypto provider by using
    // setFips() method
    const val = crypto.setFips(true);

    // Display the result
    console.log("FIPS compliant crypto"
        + " provider has been enabled")

} catch (e) {

    // Display error if any
    console.log("FIPS mode is not available.");
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
FIPS mode is not available.
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// crypto.setFips() method

// Importing crypto module
const crypto = require('crypto')

// Enabling the FIPS compliant 
// crypto provider by using
// setFips() method
try {

    // Function call
    const val = crypto.setFips(false);

    // Display the result
    console.log("FIPS compliant crypto "
        + "provider has been disabled");
} catch (e) {
    console.log("ERR_CRYPTO_FIPS_UNAVAILABLE")
}
```

**输出:**

```
ERR_CRYPTO_FIPS_UNAVAILABLE
```

**参考:**[https://nodejs . org/dist/latest-v15 . x/docs/API/crypt . html # crypto _ setfips _ bool](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_crypto_setfips_bool)