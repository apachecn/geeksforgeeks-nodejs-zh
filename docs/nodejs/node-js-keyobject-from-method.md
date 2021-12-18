# Node.js KeyObject.from()方法

> 原文:[https://www . geesforgeks . org/node-js-key object-from-method/](https://www.geeksforgeeks.org/node-js-keyobject-from-method/)

**keyObject.form()** **方法**是加密模块中类 keyObject 的内置应用编程接口，用于转换 keyObject 中的加密密钥实例。它是 KeyObject 类的静态方法。

**语法:**

```js
keyObject.form( key ) 
```

**参数:**该方法只取一个参数描述如下。

*   **Key:** This parameter holds the key value of the password.

**返回值:**该方法将实例返回给 KeyObject。

**示例:**

**文件名:index . js**

## 【JavaScript】

```js
// Node.js program to demonstrate the
// keyObject.form() method

// Importing the crypto module
const { webcrypto: { subtle }, KeyObject }
    = require('crypto');

// Generating the crypto key that is
// not a keyObject instance
(async function () {
    const key = await subtle.generateKey({
        name: 'HMAC',
        hash: 'SHA-256',
        length: 256
    }, true, ['sign', 'verify']);

    try {

        // Calling keyObject.form() method to
        // get the instance to keyObject
        const keyObject = KeyObject.from(key);
        console.log("Successfully converted a "
        + "cryptoKey to instance of keyObject");
    }
    catch (error) {
        console.log("Error has been occured");
    }
})();
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Successfully converted a cryptoKey to instance of keyObject.
```

**参考**:[https://nodejs . org/API/crypto . html # crypt _ class _ key object](https://nodejs.org/api/crypto.html#crypto_class_keyobject)