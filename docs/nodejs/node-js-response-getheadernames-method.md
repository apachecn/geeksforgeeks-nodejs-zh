# node . js response . getheadernames()方法

> 原文:[https://www . geesforgeks . org/node-js-response-getheadernames-method/](https://www.geeksforgeeks.org/node-js-response-getheadernames-method/)

***response . GetHeadernames()***(在 v7.7.0 中添加)方法是“ *http* ”模块的内置应用程序编程接口，它返回一个包含当前传出标头的唯一名称的数组。所有标题名称都是小写的。

当标题设置为 *response.setHeader()* 时，它们将与传递给 *response.writeHead()* 的任何标题合并，优先传递给 *response.writeHead()* 的标题。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

**语法:**

```js
const http = require('http');

```

**语法:**

```js
response.getHeaderNames()

```

**参数:**该属性不接受任何参数。

**返回值:**它以字符串格式返回所有标题的名称，如下例所述。

下面的例子说明了 Node.js 中*response . getheadernames()*方法的使用

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// response.getHeaderNames() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
           function(req, response) {

  // Setting up Headers
  response.setHeader('Alfa', 'Beta');
  response.setHeader('Foo', 'bar');
  response.setHeader('Set-Cookie', 
           ['foo=bar', 'bar=baz']);

  const headerNames = response.getHeaderNames();
  console.log(headerNames);
  response.end("200, ok");
});

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log(
     "Server is running at port 3000...");
});
```

**输出:**

> **输出:**在控制台
> 
> >>服务器正在端口 3000 上运行…
> 
> > >[ 'alfa '，' foo '，' set-cookie' ]

现在在浏览器中运行 *http://localhost:3000/* 。

**输出:**在浏览器中

```js
200, ok
```

**示例 2:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// response.getHeaderNames() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
           function(req, response) {

  // Setting up Headers
  response.setHeader('Alfa', 'Beta');
  response.setHeader('Alfa1', '');
  response.setHeader('Alfa2', 5);
  response.setHeader('Cookie-Setup', 
  ['Alfa=Beta', 'Beta=Romeo']);

  // Getting the set Headers
  const headers = response.getHeaders();
  const headerNames = response.getHeaderNames();

  // Printing those headers
  console.log(headers);

  // Printing headerNames
  console.log(headerNames);

  var Output = "Hello Geeksforgeeks...,"
     + " Available headerNames are:"
     + JSON.stringify(headerNames);

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

> **输出:**在控制台
> 
> 服务器正在端口 3000 上运行…
> 
> > >[对象:空原型]{ 0
> 
> 阿尔法:贝塔，
> 
> alfa1:“，
> 
> 阿尔法 2: 5，
> 
> cookie-setup”:[' Alfa = Beta '，' Beta =罗密欧']}
> 
> >[' alpha '、' alfa 1 '、' alfa 2 '、' cookie 设置']

现在在浏览器中运行 *http://localhost:3000/* 。

**输出:**在浏览器中

> Hello Geeksforgeeks…，可用的标题和预告片有:{“Alfa 1”“”、“cookie-setup”:[“Alfa = Beta”、“Beta = Romeo”]，
> 
> “内容类型”:“文本/纯文本”、“预告片”:“内容-MD5”}好的

**参考:**[https://nodejs . org/API/http . html # http _ response _ getheadernames](https://nodejs.org/api/http.html#http_response_getheadernames)