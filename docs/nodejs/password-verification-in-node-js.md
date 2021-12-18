# node . js 中的密码验证

> 原文:[https://www . geesforgeks . org/密码-节点内验证-js/](https://www.geeksforgeeks.org/password-verification-in-node-js/)

在用于密码散列和验证的节点中，我们可以使用一个名为 bcryptjs [的 npm 库。](https://www.npmjs.com/package/bcryptjs)

**安装 bcryptjs:** Node.js 包含一个内置的加密模块的 randomBytes 接口，用于获取安全随机数。

```js
npm install bcryptjs
```

**进场:**

*   要散列密码，请使用*bcrypt . hash(platextpassword，salt，callback)* ，如果没有传递回调，它将返回一个承诺。
*   要使用哈希密码验证纯文本密码，请使用 *bcrypt.compare(纯文本密码，哈希密码，回调)*，如果没有回调通过，它也会返回一个承诺。

**例 1:**

```js
// Use bcryptjs module
const bcrypt = require("bcryptjs");

// Store the password into variable
const password = "password123";

// Use bcrypt.hash() function to hash the password
bcrypt.hash(password, 8, (err, hashedPassword) => {
    if (err) {
        return err;
    }

    // Display the hashed password
    console.log(hashedPassword);

    // Use bcrypt.compare() function to compare
    // the password with hashed password
    bcrypt.compare(password, hashedPassword, (err, isMatch) => {
        if( err ) {
            return err;
        }

        // If password matches then display true
        console.log(isMatch);
    });
});
```

**输出:**

```js
$2a$08$PV4rYpBwXUPAGuMedxUnAOxq/TozK9o/QSUWaKE1XL8psOyZ.JL4q
true
```

**例 2:**

```js
// Use bcryptjs module
const bcrypt = require("bcryptjs");

// Store the password into variable
const password = "password123";

// Use bcrypt.hash() function to hash the password
bcrypt.hash(password, 8).then(hashedPassword => {

    // Display the hashed password
    console.log(hashedPassword);

    // Compare the password with hashed password
    // and return its value 
    return bcrypt.compare(password, hashedPassword);

}).then(isMatch => {

    // If password matches then display true
    console.log(isMatch);
}).catch(err => {

    // Display error log
    console.log(err);
});
```

**输出:**

```js
$2a$08$LKZU9S9WVs3C.S/zpu2U7eua/ocfzD1ytF68QPT5M600auT6M.SxG
true
```