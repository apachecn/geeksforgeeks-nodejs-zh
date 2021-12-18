# Node.js URL.password API

> 原文:[https://www.geeksforgeeks.org/node-js-url-password-api/](https://www.geeksforgeeks.org/node-js-url-password-api/)

**url.password** 是 **url** 模块内置的 **url** 类应用编程接口，用于获取和设置 URL 的密码部分。

**语法:**

```
const url.password
```

**返回值:**获取并设置 URL 的密码部分。
下面的程序说明了**网址.密码**方法的使用:
**示例 1:**

## java 描述语言

```
// node program to demonstrate the 
// url.password API as Setter 

//importing the module 'url'
const http = require('url');

// creating and initializing myURL
const myURL = new URL('https://pqr:abc@example.com');

// Display password
// value of myURL before change
console.log("Before Change");
console.log(myURL.password);

// assigning password portion
// using password API
console.log();

// Changing the myUrl.password for the above URL
myURL.password = '123';

// Display the changed password
// value of myURL after change
console.log("After Change");
console.log(myURL.href);
```

**输出** :

![](img/279811a9229aef47d5ed2a11cec73a81.png)

**例 2:**

## java 描述语言

```
// node program to demonstrate the 
// url.password API as Getter 

//importing the module 'url'
const http = require('url');

// creating and initializing myURL
const myURL = new URL('https://example.org/foo#ram');
myURL.password = '1234'

// getting the password portion
// using password
const password = myURL.password;

// Display hostname value 
console.log("password is : "+password);
console.log(myURL.href);
```

**输出:**

![](img/6d51f6cfb1b817ef87b835155bda40a0.png)

**注意:**以上程序将使用 Node 中的 **myapp.js 命令**编译运行。
**参考:**
[https://nodejs.org/api/url.html#url_url_password](https://nodejs.org/api/url.html#url_url_password)