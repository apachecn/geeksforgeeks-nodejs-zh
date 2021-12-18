# Node.js hash.update()方法

> 原文:[https://www.geeksforgeeks.org/node-js-hash-update-method/](https://www.geeksforgeeks.org/node-js-hash-update-method/)

**hash.update( )** 方法是加密模块 hash 类的内置函数。这用于用给定的数据更新散列。可以多次调用此方法来更新哈希的内容，因为此方法可以采用流数据，如文件读取流。

该函数将数据作为参数来生成哈希，它可以是字符串或文件对象。除了数据，它还采用数据的编码类型，可以是 utf-8、二进制或 ASCII。如果没有提供编码，并且数据是一个字符串，那么使用 utf-8。

**模块安装:**使用以下命令安装所需模块:

```
npm install crypto
```

**语法:**

```
hash.update(data [,Encoding])
```

**参数:**该函数取以下两个参数:

*   **数据:**需要添加到哈希中的数据。
*   **编码:**数据的编码类型。

**返回值:**这个方法返回一个有更新数据的对象。

**例 1:**

## Javascript

```
// Import crypto module
const crypto = require('crypto');

// Create Hash instance with createHash
var hash = crypto.createHash('sha256')
                            // Use update to add data
                            .update('I love GeeksForGeeks')

                            // Use digest to get the hash value
                            .digest('hex');

// Prints the hash value
console.log("Hash Value : " + hash);
```

**输出:**

```
Hash Value : 5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
```

**例二:**

## Javascript

```
// Import crypto module
const crypto = require('crypto');

// Create Hash instance with createHash
var hash = crypto.createHash('sha256')
                            // Use update to add data
                            .update('I love GeeksForGeeks')

                            // Use update to add data
                            .update('Because I love coding')

                            // Use digest to get the hash value
                            .digest('hex');

// Prints the hash value
console.log("Hash Value : " + hash);
```

**输出:**

```
Hash Value : e0789790d7da870830a679828c722f74f3840d4a6483f5babfb62c4d19884c9e
```

**参考:**[https://nodejs . org/API/crypto . html # crypto _ hash _ update _ data _ input encoding](https://nodejs.org/api/crypto.html#crypto_hash_update_data_inputencoding)