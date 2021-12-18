# Node.js crypto.scryptSync()函数

> 原文:[https://www . geesforgeks . org/node-js-crypto-scryptsync-function/](https://www.geeksforgeeks.org/node-js-crypto-scryptsync-function/)

**crypto.scryptSync()** 是一个内置函数，它在 Node.js 中提供同步的 scrypt 实现。scrypt 是一个基于密码的密钥派生函数。它的计算成本和内存成本都很高。因此，暴力攻击是不成功的。

**语法:**

```
crypto.scryptSync(password, salt, keylen[, options])
```

**参数:**该方法接受五个参数，如上所述，如下所述:

*   **密码:**可以保存字符串、Buffer、TypedArray 或 DataView 类型的数据。
*   **salt:** 它保存字符串、缓冲区、类型数据或数据视图类型的数据。它必须尽可能独特。此外，建议 salt 应该是随机的，长度至少为 16 字节。
*   **keylen:** 表示钥匙的长度，必须是数字。
*   **选项:**类型为 Object，有七个参数，分别是 cost、blockSize、并行化、N、r、p、maxmem。

**返回值**:返回一个缓冲区。

以下示例说明了在 Node.js 中使用 crypto.scryptSync()方法:

**例 1:**

## app.js

```
// Example of  crypto.scryptSync() Method

// Including crypto module in the app.js. 
import crypto from 'crypto'

// Calling scryptSync() method with some of its parameter 
const keyExample = crypto.scryptSync('GeeksforGeeks', 
                                     'gfggfg', 32);

// Prints result key as buffer 
console.log("The key in the form of buffer is:",keyExample);  

// Calling scryptSync() method with the parameter N 
const keyExample2 = crypto.scryptSync('GFG_ARTICLE', 'GFGGFG', 64, { N: 512 });

// Prints result key as buffer 
console.log("The key in the form of buffer is :",keyExample2);
```

```
node app.js
```

**输出:**

```
The key in the form of buffer is : <Buffer 
d9 9d b7 7e 7c 25 cb 39 db 3b 16 6b b8 47 73 43 4e 
96 72 9c 02 b3 55 7b 7d 66 f5 54 e6 e3 a0 e6>

The key in the form of buffer is : <Buffer 
26 c4 91 3f a7 03 b8 30 7a b5 bf a6 fe de 34 aa 46 
8c b5 dd b6 0d ce 5a 5e 03 91 a1 7c 7d ba d0 5b d6 
62 8e 11 3a 45 f6 41 a2 be b2 39 c9 57 5a 78 55 ... 
14 more bytes>
```

**例 2:**

## app.js

```
// Example of  crypto.scryptSync() Method

// Including crypto module in the app.js. 
import crypto from 'crypto'

// Defining salt as typed array 
 const arr = new Float64Array(8.0)

// Calling scryptSync() method with some of its parameter 
const keyExample = crypto.scryptSync('gghhgh', arr, 16);

// Prints result key as buffer 
console.log("The key in the form of ASCII is :"
             ,keyExample.toString("ascii")); 

// Defining salt as data view 
const arr1= new DataView(new ArrayBuffer(17)); 

// Calling scryptSync() method with the parameter N 
const keyExample2 = crypto.scryptSync('jbjbb', arr1, 16, { N: 16 });

// Prints result key as buffer 
console.log("The key in the form of hex is :",keyExample2.toString('hex'));
```

```
node app.js
```

**输出:**

```
The key in the form of ASCII is: k&q0Y4EQ_72
The key in the form of hex is : 
29dcb56a3d91f7be66de7444bc7ac605
```