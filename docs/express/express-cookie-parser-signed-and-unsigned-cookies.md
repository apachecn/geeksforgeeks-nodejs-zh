# 快速 Cookie 解析器-已签名和未签名 Cookie

> 原文:[https://www . geesforgeks . org/express-cookie-parser-signed-and-unsigned-cookies/](https://www.geeksforgeeks.org/express-cookie-parser-signed-and-unsigned-cookies/)

cookie 是随请求发送到客户端的一段数据，由用户当前使用的网络浏览器存储在客户端。借助饼干-

*   网站很容易记住用户的信息
*   很容易捕捉用户的浏览历史
*   它在存储用户会话时也很有用

会话使用秘密标识向所有服务器发出请求。信息存储在链接到此机密标识的服务器上。
为了在我们的应用程序中使用 cookie，使用了 **cookie 解析器中间件**。要安装它，请编写以下命令–

```
npm install cookie-parser@latest --save
```

另外，要安装**快速中间件**，请编写以下命令–

```
npm install express@latest --save
```

这些命令将安装最新版本的 cookie-parser 和 express。
Cookie 解析器中间件用于解析客户端向服务器发出的请求所附带的 Cookie。因此，为了使用 cookie 解析器，我们将在 JavaScript 文件中编写以下代码行——

```
const cookieParser = require('cookie-parser');
const express = require('express')

const app = express();
app.use(cookieParser());
```

让我们看一个如何设置新 cookie 的例子。创建一个名为“index.js”的新文件。要为 cookie 设置和分配名称，请遵循以下代码–

```
const express = require('express');
const cookieParser = require('cookie-parser');

const app = express();

app.get('/', (req, res) => {
   res.cookie('name', 'GeeksForGeeks').send('Cookie-Parser');
});

app.listen(3000, (err) => {
    if(err){ console.log(err) } 
    else { console.log('Success!!') }
});
```

在这里，我们将 cookie 发送到新的路由，并将 cookie 的名称设置为“GeeksForGeeks”。在最后一段代码中，我们的服务器正在监听带有回调函数的端口 3000。如果出现错误，回调函数将返回错误，否则将返回“成功”。
现在，使用命令运行以下代码–

```
node index.js
```

要检查是否设置了 cookie，只需在成功设置服务器后转到[这个](http://localhost:3000/)链接。打开控制台，将命令写成–

```
document.cookie
```

您将获得如下输出–

```
"name=GeeksForGeeks"
```

此外， **cookie 解析器中间件**用发送到服务器的名称填充 **req.cookies** 。在这里，在我们的例子中，我们可以在我们的路由中添加以下代码行–

```
console.log(req.cookies)
```

上一行的输出将是–

```
{ name: 'GeeksForGeeks' }
```

### cookie 解析器的方法

*   **cookieParser(secret, options)**

    –该中间件采用两个参数。第一个是秘密身份证，另一个是选项。秘密标识可以是字符串或字符串数组。如果没有提供秘密参数，那么它将把 cookie 作为**未签名的 cookie** 。因此，提供秘密标识是可选的。第二个参数将是一个对象，指定对 cookies 采取什么操作。例如，**解码**是一个解码 cookie 值的函数。

*   **cookieParser.JSONCookie(str)**

    –该方法将把 cookie 的值解析为 JSON cookie。如果提供的 cookie 是 JSON cookie，它将返回解析后的 JSON 值。如果不是 JSON cookie，它将返回传递的值本身。

*   **cookieParser.JSONCookies(cookies)**

    –提供一个附加了标识的对象。该方法将遍历提供的对象标识，并对每个值调用“JSONCookie”。它将用解析后的值替换原始值。这将返回传入的同一对象。

*   **cookieParser.signedCookie(string, secret)**

    –此方法将 cookie 解析为签名 cookie。如果 cookie 是已签名的 cookie，并且签名可以被验证，那么它将返回已解析的未签名值。如果 cookie 是无符号的，则返回原始值。如果 cookie 已签名，但签名无法验证，则返回 **false** 。
    现在，我们的第二个论点**秘密**可以是一串或一串数组。如果是字符串，那么它将被用作秘密。如果它是一个数组，那么将对数组的每个元素进行迭代，并使用每个秘密对 cookie 进行无符号处理。

*   **cookieParser.signedCookies(cookies, secret)**

    –此方法将对每个标识执行迭代，并检查是否有任何标识是签名 cookie。如果它被签名并且签名可以被验证，那么 ID 将被从对象中删除，它将被添加到新的返回对象中。

根据客户端发送的 cookie 的类型，将自动调用这些方法。

### 已签名和未签名 Cookie 的实现

##### 未签名的 Cookie

```
const express = require('express');
const cookieParser = require('cookie-parser');

const app = express();

app.get('/', (req, res) => {
   res.cookie('name', 'GeeksForGeeks').send();
   console.log(req.cookies);

});

app.listen(3000, (err) => {
    if(err){ console.log(err) } 
    else { console.log('Success!!') }
});
```

上述代码的输出将是–

```
"name=GeeksForGeeks"
```

##### 签名 Cookie

```
var express = require('express')
var cookieParser = require('cookie-parser')

var app = express()
app.use(cookieParser('GFG'))

app.get('/', function (req, res) {
  res.cookie('name', 'GeeksForGeeks', { signed: true }).send();
  console.log(req.signedCookies)
})

app.listen(3000, (err) => {
  if(err) { console.log(err) }
  else { console.log('Success') }
})
```

这里，在第 4 行—“GFG”是作为 cookie 的秘密值提供的。
在第 7 行–cookie 的名称设置为“GeeksForGeeks”，签名的对象设置为 true。
上述代码的输出将是–

```
{ name: 'GeeksForGeeks' }
```