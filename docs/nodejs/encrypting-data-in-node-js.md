# 加密 Node.js 中的数据

> 原文:[https://www.geeksforgeeks.org/encrypting-data-in-node-js/](https://www.geeksforgeeks.org/encrypting-data-in-node-js/)

节点中的加密和解密可以通过安装和实现“加密”库来完成。如果您已经通过手动构建安装了 Node.js，那么加密库就有可能没有附带。您可以运行
以下命令来安装加密依赖项。

```js
npm install crypto --save
```

但是如果您已经使用预构建的软件包安装了它，则不需要这样做。
**在节点中实现加密的示例。**T3】

## java 描述语言

```js
// Nodejs encryption with CTR
const crypto = require('crypto');
const algorithm = 'aes-256-cbc';
const key = crypto.randomBytes(32);
const iv = crypto.randomBytes(16);

function encrypt(text) {
let cipher = crypto.createCipheriv('aes-256-cbc',Buffer.from(key), iv);
let encrypted = cipher.update(text);
encrypted = Buffer.concat([encrypted, cipher.final()]);
return { iv: iv.toString('hex'), encryptedData: encrypted.toString('hex') };
}

function decrypt(text) {
let iv = buffer.from(text.iv, 'hex');
let encryptedText = Buffer.from(text.encryptedData, 'hex');
let decipher = crypto.createDecipheriv('aes-256-cbc', Buffer.from(key), iv);
let decrypted = decipher.update(encryptedText);
decrypted = Buffer.concat([decrypted, decipher.final()]);
return decrypted.toString();
}

var gfg = encrypt("GeeksForGeeks");
console.log(gfg);
console.log(decrypt(gfg));
```

**输出**T2】

![](img/5fadb97d33419a5ebe89f0aa2f734afc.png)