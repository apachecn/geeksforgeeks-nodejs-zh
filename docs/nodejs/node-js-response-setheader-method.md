# Node.js response.setHeader()方法

> 原文:[https://www . geesforgeks . org/node-js-response-set header-method/](https://www.geeksforgeeks.org/node-js-response-setheader-method/)

***response.setHeader(名称，值)*** (在 v0.4.0 中添加)方法是“ *http* ”模块的内置应用程序编程接口，为隐式头设置单个头值。如果此标头已经存在于要发送的标头中，则其值将被替换。在这里使用字符串数组发送多个同名的标题。非字符串值将被存储而不被修改。因此， *response.getHeader()* 可能会返回非字符串值。但是，非字符串值将被转换为字符串，用于网络传输。

当标题设置为 *response.setHeader()* 时，它们将与传递给 *response.writeHead()* 的任何标题合并，优先传递给 *response.writeHead()* 的标题。

为了得到响应和正确的结果，我们需要导入‘http’模块。

**语法:**

```
const http = require('http');

```

**语法:**

```
response.setHeader(name, value)

```

**参数:**该属性接受如上所述的单个参数，如下所述:

*   **名称** < *字符串* > **:接受表头名称，不区分大小写。**
*   **值** < *任意* > **:** 可以接受对象、字符串、整数、数组等任意值。

**返回值:**不返回值，而是设置一个表头，如下所述。

下面的例子说明了 Node.js 中 *response.setHeader()* 属性的使用

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// response.setHeaders() Method

// Importing http module
var http = require('http');
// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
       function(request, response) {

  // Setting up Headers
  response.setHeader('Content-Type', 'text/html');
  response.setHeader('Set-Cookie', ['type=ninja', 
  'language=javascript']);

  // Checking and  printing the headers
  console.log("When Header is set a string:", 
  response.getHeader('Content-Type'));
  console.log("When Header is set an Array:", 
  response.getHeader('Set-Cookie'));

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

现在在浏览器中运行 *http://localhost:3000/* 。

**输出:**

> 在控制台中
> 
> >>服务器正在端口 3000 上运行…
> 
> >>当标题设置为字符串时:文本/html
> 
> >>当 Header 设置为数组时:['type=ninja '，' language=javascript']
> 
> > >[对象:空原型] {“内容类型”:“文本/html”、“set-cookie”:[“类型=ninja”、“语言= JavaScript”]}

**示例 2:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// response.setHeaders() Method

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
  // response.setHeader('', 'Beta'); // Throws Error
  // response.setHeader(); // Throws Error

  // Checking and  printing the headers
  console.log("When Header is set an Array:", 
  response.getHeader('Cookie-Setup'));
  console.log("When Header is set an 'Beta':", 
  response.getHeader('Alfa'));
  console.log("When Header is set '':", 
  response.getHeader('Alfa1'));
  console.log("When Header is set number 5:", 
  response.getHeader('alfa2'));
  console.log("When Header is not set:", 
  response.getHeader('Content-Type'));

  // Getting the set Headers
  const headers = response.getHeaders();

  // Printing those headers
  console.log(headers);

  var Output = "Hello Geeksforgeeks..., "
      + "Available headers are:"
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

```
node index.js

```

**输出:**

> **输出:**在控制台
> 
> 服务器正在端口 3000 上运行…
> 
> 当标题设置为数组时:['阿尔法=贝塔'，'贝塔=罗密欧']
> 
> 当标题设置为“测试版”时:测试版
> 
> 当设置“标题”时:
> 
> 当表头设置为 5: 5 时
> 
> 未设置标题时:未定义
> 
> [对象:空原型]{ 0
> 
> 阿尔法:贝塔，
> 
> alfa1:“，
> 
> 阿尔法 2: 5，
> 
> cookie-setup”:[' Alfa = Beta '，' Beta =罗密欧']}

现在在浏览器中运行***http://localhost:3000/***。

> **输出:**在浏览器中
> 
> Hello Geeksforgeeks…，可用的标题有:{“Alfa”:“Beta”、“Alfa 1”:“Alfa 2”:5、“cookie-setup”:[“Alfa = Beta”、“Beta =罗密欧”]}好的

如果调用 *response.writeHead()* 方法，而这个方法还没有被调用，那么它会直接把提供的头值写到网络通道上，而不在内部缓存，头上的 *response.getHeader()* 不会产生预期的结果。如果希望对标题进行渐进式填充，以便将来进行检索和修改，请使用 *response.setHeader()* 代替 *response.writeHead()* 。

**参考:**[https://nodejs . org/API/http . html # http _ response _ set header _ name _ value](https://nodejs.org/api/http.html#http_response_setheader_name_value)