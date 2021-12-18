# 使用 bcryptjs 模块在 Node.js 中进行密码加密

> 原文:[https://www . geesforgeks . org/password-encryption-in-node-js-using-bcryptjs-module/](https://www.geeksforgeeks.org/password-encryption-in-node-js-using-bcryptjs-module/)

提交表单时，有些敏感数据(如密码)不能被任何人看到，甚至数据库管理员也不能看到。为了避免敏感数据被任何人看到，Node.js 使用了“bcryptjs”。

该模块支持将密码存储为哈希密码，而不是明文。

**安装加密模块:**

*   您可以访问安装加密模块的链接。您可以使用此命令安装此软件包。

```
npm install bcryptjs
```

*   安装 bcryptjs 模块后，您可以使用命令在命令提示符下检查您的请求版本。

```
npm version bcryptjs
```

*   之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```
node index.js
```

## index.js

```
// Requiring module
const bcrypt = require('bcryptjs');

const password = 'pass123';
var hashedPassword;

// Encryption of the string password
bcrypt.genSalt(10, function (err, Salt) {

    // The bcrypt is used for encrypting password.
    bcrypt.hash(password, Salt, function (err, hash) {

        if (err) {
            return console.log('Cannot encrypt');
        }

        hashedPassword = hash;
        console.log(hash);

        bcrypt.compare(password, hashedPassword, 
            async function (err, isMatch) {

            // Comparing the original password to
            // encrypted password   
            if (isMatch) {
                console.log('Encrypted password is: ', password);
                console.log('Decrypted password is: ', hashedPassword);
            }

            if (!isMatch) {

                // If password doesn't match the following
                // message will be sent
                console.log(hashedPassword + ' is not encryption of ' 
                + password);
            }
        })
    })
})
```

**运行应用程序的步骤:**使用以下命令运行应用程序:

```
node index.js
```

**输出:**我们将在控制台屏幕上看到以下输出。

> $ 2a $ 10 $ 4 drbplbjko 7 wul 2 ndpluralingny 7t18/zzbfncw 3 hdwfgm
> 加密密码为:pass123
> 解密密码为:$ 2a $ 10 $ 4 drbplbjko 7 wul 2 ndpluralingny 7t18/zzbfncw 3 hdwfgm