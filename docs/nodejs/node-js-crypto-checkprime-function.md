# Node.js crypto.checkPrime()函数

> 原文:[https://www . geesforgeks . org/node-js-crypto-check prime-function/](https://www.geeksforgeeks.org/node-js-crypto-checkprime-function/)

**crypto.checkPrime()** 是加密模块中加密类的内置应用程序编程接口，用于检查传递的缓冲区对象是否是 Prime。

**语法:**

```
const crypto.checkPrime(candidate[, options, [callback]])
```

**参数**:该 API 以以下参数为参数。

*   **Candidate:** It is a buffer object that represents a big octet sequence of any length.
*   **Option:** Any other option that will change the operation of the application programming interface.
*   **Callback:** is an executed callback function, which is passed as an optional parameter.

**返回值**:当且仅当候选项为素数时，该 API 返回 true。

**例 1:**

## index.js

```
// Node.js program to demonstrate the  
// crypto.checkPrime() api

// Importing crypto module
const crypto = require('crypto')

// Creating and ini
tializing new 
// ArrayBuffer object
const buffer = new ArrayBuffer(8)

// Checking if the buffer object is prime or not
// by using checkPrime() method
crypto.checkPrime(buffer, (err, val) => {

    // Checking if any error is found
    if (err) throw new Error('Uh oh!');

    // Display the result
    if (val)
        console.log("candidate is a prime")
    else
        console.log("candidate is not a prime")
})
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
candidate is not a prime
```

**例 2:**

## index . js

```
// Node.js program to demonstrate the  
// crypto.checkPrime() api

// Importing crypto module
const crypto = require('crypto')

// Creating and initializing new 
// ArrayBuffer object
const buffer = BigInt("0o377777777777777777")

// Checking if the buffer object is prime or not
// by using checkPrime() method
crypto.checkPrime(buffer, (err, val) => {

    // Checking if any error is found
    if (err) throw new Error('Uh oh!');

    // Display the result
    if (val)
        console.log("candidate is a prime")
    else
        console.log("candidate is not a prime")
})
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
candidate is not a prime
```

**参考:**

[https://nodejs . org/dist/latest-v 15 . x/docs/API/crypto . html # crypto _ crypto _ check prime _ 候选者 _options_callback](https://nodejs.org/dist/latest-v15.x/docs/api/crypto.html#crypto_crypto_checkprime_candidate_options_callback)