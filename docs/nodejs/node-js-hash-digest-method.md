# Node.js hash.digest()方法

> 原文:[https://www.geeksforgeeks.org/node-js-hash-digest-method/](https://www.geeksforgeeks.org/node-js-hash-digest-method/)

**hash.digest( )** 方法是加密模块的 **Hash 类**的内置函数。这用于创建创建哈希时传递的数据摘要。例如，当我们创建一个散列时，我们首先使用 crypto.createhash()创建一个散列实例，然后使用 **update( )** 函数更新散列内容，但是到目前为止，我们还没有得到结果散列值，所以要得到散列值，我们使用 Hash 类提供的摘要函数。

该函数以一个**字符串**作为输入，定义返回值的**类型**，例如**十六进制**或 **base64** 。如果您离开此字段，您将获得**缓冲区**。

**语法:**

```js
hash.digest([encoding])
```

**参数:**该函数取以下一个参数:

*   **Code:** This method takes an optional parameter to define the type of returned output. You can use **' hex'** or **' base64'** as parameters.

**模块安装:**使用以下命令安装所需的模块:

```js
npm install crypto
```

**返回值:**该函数在传递参数时返回**字符串**，在没有传递参数时返回**缓冲区**对象。假设我们传递了参数 **base64** ，那么返回值将是一串 **base64** 编码。

**示例 1:** 以**十六进制**和 **base64 的形式生成字符串*的哈希值。***

<gfg-tab role="tab" slot="tab" id="gfg-tab-0">index . js</gfg-tab> <gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="javascript">```js
// Importing the crypto library
const crypto = require("crypto")

// Defining the algorithm
let algorithm = "sha256"

// Defining the key
let key = "GeeksForGeeks"

// Creating the digest in hex encoding
let digest1 = crypto.createHash(algorithm).update(key).digest("hex")

// Creating the digest in base64 encoding
let digest2 = crypto.createHash(algorithm).update(key).digest("base64")

// Printing the digests
console.log("In hex Encoding : \n " + digest1 + "\n")
console.log("In base64 encoding: \n " + digest2)
```</gfg-panel>