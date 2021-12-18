# req.cookies 和 req . signed bookies in express . js

> 原文:[https://www . geesforgeks . org/req-cookies-and-req-signed bookies-in-express-js/](https://www.geeksforgeeks.org/req-cookies-and-req-signedcookies-in-express-js/)

[**req . cookies:**](https://www.geeksforgeeks.org/express-js-req-cookies-property/)**Request。cookie 应该是来自客户端(浏览器)和响应的 cookie。cookie 是将发送回客户端(浏览器)的 cookie。Cookies 是通过服务器请求发送到客户端并存储在客户端的小文件/数据。这有助于我们跟踪用户的行为。**

**Cookie 解析器是一个中间件，用于解析附加到客户端请求对象的 cookie。当我们使用 cookie 解析器中间件时，这个属性是一个包含请求发送的 cookie 的对象。如果请求不包含 cookies，则默认为{ }。**

****示例:****

## **java 描述语言**

```js
var cookieParser = require('cookie-parser');
var express = require('express');
var app = express();
var PORT = 3000;

app.use(cookieParser());

app.get('/user', function (req, res) {
    req.cookies.name='Gourav';
    req.cookies.age=12;

    console.log(req.cookies);
    res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

****输出:**现在打开浏览器，向**http://localhost:3000/user**发出 GET 请求，现在可以在控制台上看到如下输出:**

```js
Server listening on PORT 3000
[Object: null prototype] { name: 'Gourav', age: 12 }
```

**[**req . signed bookies:**](https://www.geeksforgeeks.org/express-js-req-signedcookies-property/)**req . signed bookies 属性包含请求发送的已签名 cookie，未签名，并且在使用 cookie 解析器中间件时可以使用。对 cookie 进行签名不会使其隐藏或加密，而只是防止对 cookie 的篡改。它的工作原理是创建一个 HMAC 值(当前 cookie)，然后 base64 对其进行编码。当 cookie 被读取时，它会重新计算签名，并确保它与附加到它的签名相匹配。如果不匹配，则给出一个错误。如果没有发送签名的 cookies，则属性默认为{ }。****

******示例:******

## ****java 描述语言****

```js
**var cookieParser = require('cookie-parser');
var express = require('express');
var app = express();
var PORT = 3000;

app.use(cookieParser());

app.get('/user', function (req, res) {

    // Setting multiple cookies
    req.signedCookies.title='Gourav';
    req.signedCookies.age=12;

    console.log(req.signedCookies);
    res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});**
```

******输出:**现在打开浏览器，向**http://localhost:3000/user**发出 GET 请求，现在可以在控制台上看到如下输出:****

```js
**Server listening on PORT 3000
[Object: null prototype] { title: 'Gourav', age: 12 }**
```

******req . cookies 与 req . signed bookies 的区别–******

<figure class="table">

| **请求。饼干** | **请求。签约博彩公司** |
| We can't identify whether the data that is returning cookie has been modified by the client. | If we want to ensure that the data returned to the cookie has not been modified by the client, we use the signature cookie. |
| If the request does not contain cookies, the default is {}. | If no signed cookies are sent, this property defaults to {}. |
| The server cannot detect whether cookies have been changed by the client. | The server can detect whether cookies have been changed by the client. |
| Without adding a signature to the cookie. | The signature is added as part of the cookie together with the actual cookie data. Data from that signature cookie and secret known only to the server. |

</figure>