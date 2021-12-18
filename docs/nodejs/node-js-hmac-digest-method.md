# Node.js hmac.digest()方法

> 原文:[https://www.geeksforgeeks.org/node-js-hmac-digest-method/](https://www.geeksforgeeks.org/node-js-hmac-digest-method/)

**hmac.digest()** 方法是*加密*模块内 *hmac* 类的内置应用编程接口，用于返回输入数据的 hmac 哈希值。

**语法:**

```
hmac.digest([encoding])
```

**参数:**该方法以编码为参数，为可选参数。

**返回值:**该方法使用 *hmac.update()* 计算所有数据通路的 hmac 摘要。如果没有提供*编码*，则返回*缓冲区*，否则返回*字符串*。

**注意:***hmac . digest()*执行最终操作。所以，hmac 对象在调用 *hmac.digest()后变得不可用。*调用多个 *hmac.digest()* 导致错误。

**项目设置:**新建一个 NodeJS 项目并命名为 **hmac**

```
mkdir hmac && cd hmac
npm init -y
npm install crypto
```

现在创建一个*。js* 文件，并将其命名为 **index.js**

**例 1:**

## index.js

```
// Node.js program to demonstrate the
// crypto hmac.digest() method

// Importing crypto module
const { createHmac } = require('crypto')

// Creating and initializing algorithm
// and password
const algo = 'sha256'
const secret = 'GFG Secret Key'

// Create an HMAC instance
const hmac = createHmac(algo, secret)

// Update the internal state of
// the hmac object
hmac.update('GeeksForGeeks')

// Perform the final operations
// No encoding provided
// Return calculated hmac hash
// value as Buffer
let result = hmac.digest()

// Check whether returns value is
// instance of buffer or not
console.log(Buffer.isBuffer(result)) // true

// Convert buffer to string
result = result.toString('hex')

// Print the result
console.log(`HMAC hash: ${result}`)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> true
> hmac hash:c8ae 3 e 09855 AE 7 AC 3405 ad 60d 93758 EDC 0 ccebc 1 cf 5 c 529 bfb 5d 058674695 c 53

**例 2:**

## index.js

```
// Node.js program to demonstrate the    
// crypto hmac.digest() method

// Defining myfile
const myfile = process.argv[2];

// Includes crypto and fs module
const crypto = require('crypto');
const fs = require('fs');

// Creating and initializing 
// algorithm and password
const algo = 'sha256'
const secret = 'GFG Secret Key'

// Creating Hmac
const hmac = crypto.createHmac(algo, secret);

// Creating read stream
const readfile = fs.createReadStream(myfile);

readfile.on('readable', () => {

    // Calling read method to read data
    const data = readfile.read();

    if (data) {

        // Updating
        hmac.update(data);
    } else {

        // Perform the final operations 
        // Encoding provided
        // Return hmac hash value
        const result = hmac.digest('base64')

        // Display result
        console.log(
    `HMAC hash value of ${myfile}: ${result}`);
    }
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js package.json
```

**输出:**

```
HMAC hash value of package.json: 
L5XUUEmtxgmSRyg12gQuKu2lmTJWr8hPYe7vimS5Moc=
```

**参考:**[https://nodejs . org/API/crypto . html # crypto _ hmac _ digest _ encoding](https://nodejs.org/api/crypto.html#crypto_hmac_digest_encoding)