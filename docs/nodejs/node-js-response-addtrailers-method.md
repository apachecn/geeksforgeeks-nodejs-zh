# node . js response .add 拖车()方法

> 原文:[https://www . geesforgeks . org/node-js-response-add 拖车-method/](https://www.geeksforgeeks.org/node-js-response-addtrailers-method/)

***response .add 拖车()*** (在 v0.3.0 中添加)方法是“ *http* ”模块的内置应用程序编程接口，它将 http 尾部标头(一个标头，但在消息的末尾)添加到响应中。只有当响应使用分块编码时，才会发出预告片；如果不是(*例如，如果请求是 HTTP/1.0* ，它们将被无声地丢弃。HTTP 要求发送尾部头，以便发出尾部，在其值中包含一个头部字段列表。

当标题设置为 *response.setHeader()* 时，它们将与传递给 *response.writeHead()* 的任何标题合并，优先传递给 *response.writeHead()* 的标题。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

**语法:**

```js
const http = require('http');

```

**语法:**

```js
response.addTrailers(headers);

```

**参数:**该属性接受如上所述的单个参数，如下所述:

*   **标头** < *字符串* > **:** 它接受 HTTP 尾随标头的名称(*一个标头，但在消息的末尾*)来响应。

**返回值:**不返回值，而是设置一个表头，如下所述。

下面的例子说明了在 Node.js 中*response .add 拖车()*属性的使用

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// response.addTrailers() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
       function(request, response) {

  // Setting up Headers
  response.setHeader('Alfa', 'Beta');

  response.writeHead(200, { 
    'Content-Type': 'text/plain', 
    'Trailer': 'Content-MD5' 
  });
  response.addTrailers({'Content-MD5': 
    '7895bf4b8828b55ceaf47747b4bca667'});

  console.log(response.getHeaders());
  response.end('Trailer Added, ok');
});

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log(
      "Server is running at port 3000...");
});
```

现在在浏览器中运行 *http://localhost:3000/* 。

**输出:**在控制台

> >>服务器正在端口 3000 上运行…
> 
> > >[对象:空原型]{ 0
> 
> 阿尔法:贝塔，
> 
> 内容类型':'文本/纯文本'，
> 
> 预告片:' '内容-MD5'}

**输出:**在浏览器中

```js
Trailer Added, ok
```

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the 
// response.addTrailers() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
          function(req, response) {

  // Setting up Headers
  response.setHeader('Alfa1', '');
  response.setHeader('Cookie-Setup', 
       ['Alfa=Beta', 'Beta=Romeo']);

  response.writeHead(200, { 
    'Content-Type': 'text/plain', 
    'Trailer': 'Content-MD5' 
  });

  // addTrailers Content-MD5 
  response.addTrailers({'Content-MD5': 
    '7895bf4b8828b55ceaf47747b4bca667'});

  // Adding Cookie-Setup as trailer 
  // ( Not gets added as trailer )
  response.addTrailers({ 'Cookie-Setup': 
       ['Alfa=Beta', 'Beta=Romeo'] });

  // Checking and printing the headers
  console.log("Calling trailer by getHeader :", 
  response.getHeader('Content-MD5'));

  // console.log("Calling trailer by getHeader :", 
  response);

  // Getting the set Headers
  const headers = response.getHeaders();

  // Printing those headers
  // Header
  console.log("Printing _header: ", response._header);

  // Trailer
  console.log("Printing _trailer: ", response._trailer);

  // All headers
  console.log("Printing All headers: ", headers);

  var Output = "Hello Geeksforgeeks..., "
    + "Available headers and trailers are:"
    + JSON.stringify(headers);

  // Prints Output on the browser in response
  response.write(Output);
  response.end('ok');
});

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

> 在控制台中
> 
> 服务器正在端口 3000 上运行…
> 
> >>通过 getHeader 调用尾部:未定义
> 
> >>打印 _ 表头:HTTP/1.1 200 OK
> 
> Alfa1:
> 
> cookie-设置:阿尔法=测试版
> 
> 饼干设置:测试版=罗密欧
> 
> 内容类型:文本/纯文本
> 
> 预告片:内容-MD5
> 
> 日期:2020 年 9 月 9 日星期三格林尼治时间 06:03:32
> 
> 连接:保持活力
> 
> 传输编码:分块
> 
> >>打印 _ 预告片:Cookie-设置:阿尔法=贝塔，贝塔=罗密欧
> 
> >>打印所有标题:[对象:空原型]{ 0
> 
> alfa1:“，
> 
> cookie-setup:“['阿尔法=贝塔'，'贝塔=罗密欧']，
> 
> 内容类型':'文本/纯文本'，
> 
> 预告片:' '内容-MD5'}

现在在浏览器中运行 *http://localhost:3000/* 。

**输出:**在浏览器中

> Hello Geeksforgeeks…，可用的标题和预告片有:{“Alfa 1”“”、“cookie-setup”:[“Alfa = Beta”、“Beta = Romeo”]，
> 
> “内容类型”:“文本/纯文本”、“预告片”:“内容-MD5”}好的

**参考:**[https://nodejs . org/API/http . html # http _ response _add 拖车 _headers](https://nodejs.org/api/http.html#http_response_addtrailers_headers)