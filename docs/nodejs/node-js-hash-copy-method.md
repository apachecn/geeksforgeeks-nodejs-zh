# Node.js hash.copy()方法

> 原文:[https://www.geeksforgeeks.org/node-js-hash-copy-method/](https://www.geeksforgeeks.org/node-js-hash-copy-method/)

**hash.copy( )** 方法是加密模块 hash 类的内置函数。此方法用于复制哈希的当前状态。可以多次调用此方法来创建哈希的多个副本。如果在调用摘要方法后调用此方法，它将引发错误。

此函数接受一个可选参数来控制流行为，如输出长度。

**语法:**

```
hash.copy([,Optional ])
```

**参数:**本功能取一个参数，可选:

*   . The popularity of data is.

**返回值:**该方法返回哈希当前状态的副本。

**模块安装:**使用以下命令安装所需模块:

```
npm install crypto
```

**示例 1:** 只复制一次哈希。

## 

```
// Importing crypto module
const crypto = require('crypto');

// Creating Hash instance with createHash
const hash = crypto.createHash('sha256');

// use update to add data
hash.update('I love GeeksForGeeks');

// Making the copy of the current hash
const hashCopy = hash.copy();

// Printing the hash value
console.log("Original Hash Value : " + hash.digest('hex'));
console.log("Copied Hash Value : " + hashCopy.digest('hex'));
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Original Hash Value : 
  5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
Copied Hash Value : 
  5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
```

**示例 2:** 多次复制哈希。

## 

```
const crypto = require('crypto');

// Creating Hash instance with createHash
const hash = crypto.createHash('sha256');

// Adding data to hash
hash.update('I love GeeksForGeeks');

// Making copy of the current hash
const hashCopy1 = hash.copy();
const hashCopy2 = hash.copy();

// Printing the hash value
console.log("Original Hash Value : " + hash.digest('hex'));
console.log("Copy 1 : " + hashCopy1.digest('hex'));
console.log("Copy 2 : " + hashCopy2.digest('hex'));
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Original Hash Value : 
  5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
Copy 1 : 
  5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
Copy 2 : 
  5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
```

**示例 3:** 更新复制的哈希值。

## 

```
//Importing crypto module
const crypto = require('crypto');

// Creating Hash instance with createHash
const hash = crypto.createHash('sha256');

// Adding data to hash
hash.update('I love GeeksForGeeks');

// Making copy of the current hash
const unchangedCopy = hash.copy();
const updatedCopy = hash.copy();

// Update the old data
updatedCopy.update('Because I love coding')

// Printing the hash value
console.log("Original Hash Value : " + hash.digest('hex'));
console.log("Unchanged Copy : " + unchangedCopy.digest('hex'));
console.log("Updated Copy : " + updatedCopy.digest('hex'));
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
Original Hash Value : 
  5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
Unchanged Copy : 
  5a302d3c930d9e938c5326d7bb863afdc024b9ce77e30e99c4b82983350f8196
Updated Copy : 
  e0789790d7da870830a679828c722f74f3840d4a6483f5babfb62c4d19884c9e
```

**参考**:[https://nodejs . org/API/crypt . html # crypt _ hash _ copy _ options](https://nodejs.org/api/crypto.html#crypto_hash_copy_options)