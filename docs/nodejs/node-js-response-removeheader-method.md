# node . js response . remove header()方法

> 原文:[https://www . geesforgeks . org/node-js-response-remove header-method/](https://www.geeksforgeeks.org/node-js-response-removeheader-method/)

***response . remove header()***(*在 v0.9.3* 中添加)属性是“ *http* 模块的一个内置属性，它删除由排队等待隐式发送的名称标识的标头。标题名称匹配不区分大小写。由 *response.getHeaders()* 方法返回的对象通常不是从 JavaScript 对象继承的。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

```
const http = require('http');
```

**语法:**

```
response.removeHeader(name);
```

**参数:**该属性接受如上所述的单个参数，如下所述:

*   **名称** < *字符串* > **:接受表头名称，不区分大小写。**

**返回值**:它不返回值，而是删除一个排队等待隐式发送的头。

下面的例子说明了 Node.js 中 *response.removeHeader()* 属性的使用

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// response.removeHeader() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
           function(req, response) {

  // Setting up Headers
  response.setHeader('Alfa', 'Beta');
  response.setHeader('Cookie-Setup',
         ['Alfa=Beta', 'Beta=Romeo']);

  console.log("Before removing headers...")

  // Checking and  printing the headers
  console.log("When Header is set an Array:",
  response.hasHeader('Cookie-Setup'));

  // Removing Headers
  response.removeHeader('Cookie-Setup');

  console.log("After removing headers...")

  // Checking and  printing the headers
  console.log("When Header is set an Array:",
  response.hasHeader('Cookie-Setup'));

  // Printing those headers
  console.log(response.getHeaders());

  response.end();
});

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});
```

现在在浏览器中运行 *http://localhost:3000/* 。

**输出:**

> **输出:**(控制台中)
> 
> >>服务器正在端口 3000 上运行…
> 
> >>删除标题之前…
> 
> 当标题设置为数组时:真
> 
> >>删除标题后…
> 
> 当标题设置为数组时:假
> 
> > >[对象:空原型] {阿尔法:“测试版”}

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// response.removeHeader() Method

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

  console.log("Before removing headers...")

  // Checking and  printing the headers
  console.log("When Header is set an Array:",
  response.hasHeader('Cookie-Setup'));
  console.log("When Header is set an 'Beta':",
  response.hasHeader('Alfa'));
  console.log("When Header is set '':",
  response.hasHeader('Alfa1'));
  console.log("When Header is set number 5:",
  response.hasHeader('alfa2'));
  console.log("When Header is not set:",
  response.hasHeader('Content-Type'));

  // Removing Headers
  response.removeHeader('Cookie-Setup');
  response.removeHeader('ALFA2');

  console.log("After removing headers...")

  // Checking and  printing the headers
  console.log("When Header is set an Array:",
  response.hasHeader('Cookie-Setup'));
  console.log("When Header is set an 'Beta':",
  response.hasHeader('Alfa'));
  console.log("When Header is set '':",
  response.hasHeader('Alfa1'));
  console.log("When Header is set number 5:",
  response.hasHeader('alfa2'));
  console.log("When Header is not set:",
  response.hasHeader('Content-Type'));

  // Getting the set Headers
  const headers = response.getHeaders();

  // Printing those headers
  console.log(headers);

  var Output = "Hello GeeksforGeeks...,"
    + " Available headers are:"
    + JSON.stringify(headers);

  // Prints Output on browser in response
  response.write(Output);
  response.end();
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

> **输出:**(控制台中)
> 
> >>服务器正在端口 3000 上运行…
> 
> >>删除标题之前…
> 
> 当标题设置为数组时:真
> 
> 当标题设置为“测试版”时:真
> 
> 当“标题”设置为“真”时
> 
> 当标题设置为 5 时:真
> 
> 未设置标题时:假
> 
> >>删除标题后…
> 
> 当标题设置为数组时:假
> 
> 当标题设置为“测试版”时:真
> 
> 当“标题”设置为“真”时
> 
> 当标题设置为 5 时:假
> 
> 未设置标题时:假
> 
> > >[对象:空原型] {阿尔法:“测试版”，阿尔法 1:“}

现在在浏览器中运行***http://localhost:3000/***。

> **输出:**(在浏览器中)
> 
> Hello GeeksforGeeks…，可用的标题有:{“alfa”:“Beta”、“alfa 1”“”}

**参考:**[https://nodejs . org/API/http . html # http _ response _ remove header _ name](https://nodejs.org/api/http.html#http_response_removeheader_name)