# Node.js crypto.randomBytes()方法

> 原文:[https://www . geesforgeks . org/node-js-crypto-random bytes-method/](https://www.geeksforgeeks.org/node-js-crypto-randombytes-method/)

**crypto.randomBytes()方法**用于以密码方式生成一个**构建良好的人工随机数据和要在书面代码中生成的字节数。
**语法:**** 

```
crypto.randomBytes( size, callback )
```

****参数:**该方法接受两个参数，如上所述，如下所述:** 

*   ****大小:**类型为*号*，表示要生成的字节数。**
*   ****回调:**是由两个参数组成的函数，即 **err 和 buf** 。然而，如果回调函数在所述代码中可用，则字节异步生成，否则这些字节同步生成。**

****返回类型:**如果给定了回调函数，则返回一个 Buffer。
以下示例说明了在 Node.js:
**中使用 **crypto.randomBytes()方法**示例 1:**** 

```
// Node.js program to demonstrate the 
// crypto.randomBytes() method

// Including crypto module
const crypto = require('crypto');

// Calling randomBytes method with callback
crypto.randomBytes(127, (err, buf) => {
  if (err) {
    // Prints error
    console.log(err);
    return;
  }

  // Prints random bytes of generated data
  console.log("The random data is: "
             + buf.toString('hex'));
});
```

****输出:**这里提供回调函数，所以同步生成随机字节。** 

> **随机数据为:074 e 48 c8 e3c 0 BC 19 F9 e 22 DD 757037392 e 5d 0 BF 80 cf 9 DD 51 bb 7808872 a 511 B3
> C1 CD 91053 FCA 873 a 4 CB 7 b 2549 EC 1010 a 9 a1 a 4 C2 a 6 aceed 9d 115 EB 9d 60 a 1630 e 056 f 3 ACC 10574 CD 563
> 376d 4 e**

****例 2:**** 

```
// Node.js program to demonstrate the 
// crypto.randomBytes() method

// Including crypto module
const crypto = require('crypto');

// Calling randomBytes method without callback
const buf = crypto.randomBytes(60); 

// Prints random bytes of generated data
console.log("The random bytes of data generated is: "
                + buf.toString('utf8'));
```

****输出:**这里不提供回调函数，所以同步生成字节** 

```
The random bytes of data generated is: _??i???Z?Z?o?i?W??bEC
?F????#?-??T??jDqmm?v??7?Q?c_G?%?
```

****参考:**[https://nodejs . org/API/crypt . html # crypt _ crypt _ random bytes _ size _ callback](https://nodejs.org/api/crypto.html#crypto_crypto_randombytes_size_callback)**