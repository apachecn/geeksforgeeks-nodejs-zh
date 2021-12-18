# node . js diffihellman . set private key()方法

> 原文:[https://www . geesforgeks . org/node-js-diffihellman-set private key-method/](https://www.geeksforgeeks.org/node-js-diffiehellman-setprivatekey-method/)

**DiffieHellman . SetPrivatKey()**方法是加密模块内类 *DiffieHellman* (dh)的内置应用编程接口，用于设置 *dh* 对象的私钥。

**语法:**

```js
diffieHellman.setPrivateKey(privateKey[, encoding])
```

**参数:**该方法接受以下两个参数:

*   **Private key:** is used to represent the private key.
*   **code:** code used to represent *private key* . If the code *is provided, the private key* should be a string; otherwise, it is a buffer, type data or data view.

**例 1:**

## index . js

```js
// Node.js program to demonstrate the
// diffieHellman.setPrivateKey() Method

const crypto = require('crypto')

// Generate DH Key pair
crypto.generateKeyPair('dh', 
    {
        primeLength: 512,
         publicKeyEncoding: {
            type: 'spki',
            format: 'der'
        },
        privateKeyEncoding: {
            type: 'pkcs8',
            format: 'der'
        }
    },
    cb
)

function cb(err, publicKey, privateKey){
    // Create Diffie-Hellman instance
    const dh = crypto.createDiffieHellman(512)
    // Set the dh's privateKey
    dh.setPrivateKey(privateKey)

    if( privateKey.equals(dh.getPrivateKey()) )
        console.log("DH private Key is set successfully")
}
```

使用以下命令运行 **index.js** 文件

```js
node index.js
```

**输出:**

```js
DH private Key is set successfully
```

**例 2:**

## index . js

```js
// Node.js program to demonstrate the
// diffieHellman.setPrivateKey() Method

const crypto = require( 'crypto' )

crypto.generateKeyPair( 
    'dh', 
    { primeLength: 512 }, 
    cb 
)

function cb( err, publicKey, privateKey ){
    // Export key from KeyObject
    privateKey = privateKey.export( {type: 'pkcs8', format: 'der'} )
    // Encode key in base64
    privateKey = privateKey.toString('base64');
    // Create Diffie-Hellman instance
    const dh = crypto.createDiffieHellman( 512 )
    // Set the dh's privateKey
    dh.setPrivateKey( privateKey, 'base64' )

    if( privateKey === dh.getPrivateKey('base64')  )
        console.log( "DH private Key is set successfully" )
}
```

使用以下命令运行 **index.js** 文件

```js
node index.js
```

**输出:**

```js
DH private Key is set successfully
```

**参考:**[https://nodejs . org/API/crypto . html # crypt _ ecdh _ setprivtekey _ private key _ encoding](https://nodejs.org/api/crypto.html#crypto_ecdh_setprivatekey_privatekey_encoding)