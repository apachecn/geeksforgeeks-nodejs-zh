# Node.js hmac.update()方法

> 原文:[https://www.geeksforgeeks.org/node-js-hmac-update-method/](https://www.geeksforgeeks.org/node-js-hmac-update-method/)

**HMAC.update()** 方法是加密模块中 hmac 类的内置方法，用于更新 hmac 对象的数据。

**语法:**

```js
hmac.update(data[, inputEncoding])
```

**参数:**该方法取以下两个参数:

*   **Data:** It can be a string, Buffer, TypedArray or DataView type. What is passed to this function is data.
*   **Enter the code:** is an optional parameter. It is the encoding of the data string.

**返回值:**此方法不返回任何内容。

**项目设置:**新建一个 NodeJS 项目并命名为 **hmac** 。

```js
mkdir hmac && cd hmac
npm init -y
```

现在创建一个*。js* 文件，并将其命名为 **index.js**

**例 1:**

## index . js

```js
// Node.js program to demonstrate the
// crypto hmac.update() method

// Importing crypto module
const { createHmac } = require('crypto')

// Creating and initializing algorithm and password
const algo = 'sha256'
const secret = 'GFG Secret Key'

// Create an HMAC instance
const hmac = createHmac(algo, secret)

// Update the internal state of the hmac object
hmac.update('GeeksForGeeks')

// Perform the final operations
// Return calculated hash
const result = hmac.digest('base64')

// Print the result
console.log(`HMAC hash: ${result}`)
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
HMAC hash: yK4+CYVa56w0Ba1g2TdY7cDM68HPXFKb+10FhnRpXFM=
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the    
// crypto hmac.update() method

// Defining myfile
const myfile = process.argv[2];

// Includes crypto and fs module
const crypto = require('crypto');
const fs = require('fs');

// Creating and initializing algorithm and password
const algo = 'sha256'
const secret = 'GFG Secret Key'

// Creating Hmac
const hmac = crypto.createHmac(algo, secret);

// Creating read stream
const readfile = fs.createReadStream(myfile);

readfile.on('readable', () => {

  // Calling read method to read data
  const data = readfile.read();

  if (data)

    // Updating
    hmac.update(data);
  else {

    // Perform the final operations 
    // Return hash value
    const result = hmac.digest('hex')

    // Display result
    console.log(`HMAC hash value of ${myfile}: ${result}`);
  }
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js package.json
```

**输出:**

> 包的 HMAC 哈希值. JSON:38f 0 f 975 f 8964343 c 24 da 940188 aeb 6 bb 20842 E3 C5 BF 03 CB 66773 e 98 beeb 73

**参考:**[https://nodejs . org/API/crypto . html # crypto _ hmac _ update _ data _ input encoding](https://nodejs.org/api/crypto.html#crypto_hmac_update_data_inputencoding)