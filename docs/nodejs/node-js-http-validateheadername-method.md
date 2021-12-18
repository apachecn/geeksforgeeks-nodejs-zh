# node . js http . validateheadername()方法

> 原文:[https://www . geesforgeks . org/node-js-http-validateheadername-method/](https://www.geeksforgeeks.org/node-js-http-validateheadername-method/)

***http . validateHeadername()***(在 v14.3.0 中添加)属性是“ *http* 模块的内置属性，该模块对所提供的名称执行低级验证，这些验证是在调用 *res.setHeader(名称，值)*时完成的。将非法值作为名称传递将导致抛出*类型错误*，由代码标识:“ *ERR_INVALID_HTTP_TOKEN* ”。

在向 *HTTP* 请求或响应传递标头之前，没有必要使用此方法。 *HTTP* 模块将自动验证此类报头。

**注意:**使用最新版本的 Node.js 获取需要的输出。**T3】**

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

```
const http = require('http');
```

**语法:**

```
http.validateHeaderName(name);
```

**参数:**该属性接受如上所述的单个参数，如下所述:

*   **名称** < *字符串* > **:接受表头名称，不区分大小写。**

**返回值:**不返回值，而是验证表头是否可接受。

下面的例子说明了 Node.js 中*属性的使用*

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// http.validateHeaderName() Method

// Importing http module
var http = require('http');
const { validateHeaderName } = require('http');

try {
  validateHeaderName('');
} catch (err) {
  err instanceof TypeError; // true

  // ERR_INVALID_HTTP_TOKEN
  console.log("Error Occured", err.code);

  // Header name must be a valid
  // HTTP token [""]
  console.log(err.message);
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 在控制台
> > >中出现错误:“ERR _ INVALID _ HTTP _ TOKEN”
> >>标头名称必须是有效的 HTTP token [""]

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// http.validateHeaderName() Method

// Importing http module
var http = require('http');

// Another way to import
const { validateHeaderName } = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
  function(request, response) {

  // Setting up Headers
  response.setHeader('Content-Type', 'text/html');
  response.setHeader('Set-Cookie', ['type=ninja',
  'language=javascript']);

  // Validating headers
  try {
    validateHeaderName('Content-Type');
    console.log("Header 'Content-Type' Validated True...")
    http.validateHeaderName('set-cookie');
    console.log("Header 'set-cookie' Validated True...")
    http.validateHeaderName('alfa-beta');
    console.log("Header 'alfa-beta' Validated True...")
    validateHeaderName('@@wdjhgw');// not valid
  } catch (err) {
    err instanceof TypeError;
    console.log("Error Occured", err.code);

    // Prints 'Header name must be
    // a valid HTTP token [""]'
    console.log(err.message);
  }

  // Getting the set Headers
  const headers = response.getHeaders();

  // Printing those headers
  console.log(headers);

  // Prints Output on the browser in response
  response.writeHead(200,
    { 'Content-Type': 'text/plain' });
  response.end('ok');
});

// Listening to http Server
httpServer.listen(PORT, () => {
  console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 在控制台
> > >中，服务器正在端口 3000 处运行……
> 标头“内容-类型”验证为真……
> 标头“set-cookie”验证为真……
> 标头“阿尔法-beta”验证为真……
> 错误发生 ERR_INVALID_HTTP_TOKEN
> 标头名称必须是有效的 HTTP 令牌[" @ @ wdjgw "]
> 【对象:空原型】{
> “内容-类型”:“text/html”，
> “set-cookie”:

现在在浏览器中运行 *http://localhost:3000/* 。

**输出:**在浏览器中

```
ok
```

**参考:**[https://nodejs . org/API/http . html # http _ http _ validator adename _ name](https://nodejs.org/api/http.html#http_http_validateheadername_name)