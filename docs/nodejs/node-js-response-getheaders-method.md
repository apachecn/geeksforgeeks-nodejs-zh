# Node.js response.getHeaders()方法

> 原文:[https://www . geesforgeks . org/node-js-response-getheaders-method/](https://www.geeksforgeeks.org/node-js-response-getheaders-method/)

***response . getheaders()***(*在 v7.7.0* 中添加)方法是“http”模块的一个内置方法，它返回当前传出头的一个浅层副本。由于使用了浅拷贝，数组值可能会发生变化，而无需额外调用各种与标头相关的 *http* 模块方法。返回对象的键是头名称，值是各自的头值。所有标题名称都是小写的。

由 *response.getHeaders()* 方法返回的对象通常不会从 JavaScript 对象继承。这意味着像 *obj.toString()、obj.hasOwnProperty()、*等典型的 Object 方法没有定义，也不会起作用。

为了得到响应和正确的结果，我们需要导入‘http’模块。

```
const http = require('http');

```

**语法:**

```
response.getHeaders()

```

**参数:**该属性不接受任何参数。

**返回值** < *对象* > **:** 返回当前传出标头的浅拷贝。

下面的例子说明了 Node.js 中 *response.getHeaders()* 属性的使用

**示例:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// response.getHeaders() Method

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

  // Getting the set Headers
  const headers = response.getHeaders();

  // Printing those headers
  console.log(headers);

  // Prints Hello GeeksforGeeks... 
  // on browser in response
  response.write('Hello GeeksforGeeks...');
  response.end();
});

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log("server started at 3000...")
});
```

**输出:**

> **在 Console:**
> > >服务器在 3000 启动……
> >>【对象:空原型】{
> 阿尔法:“贝塔”、
> “cookie-setup”:[“阿尔法=贝塔”，“贝塔=罗密欧”]}
> > >【对象:空原型】{
> 阿尔法:“贝塔”、
> “cookie-setup”:[“阿尔法=贝塔”，“贝塔=罗密欧”]}

现在在浏览器中运行***http://localhost:3000/***。

**输出:**(在浏览器中)

```
Hello GeeksforGeeks...
```

参考:[https://nodejs.org/api/http.html#http_response_getheaders](https://nodejs.org/api/http.html#http_response_getheaders)