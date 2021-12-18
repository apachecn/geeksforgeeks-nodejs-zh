# node . js response . write continue()方法

> 原文:[https://www . geesforgeks . org/node-js-response-write continue-method/](https://www.geeksforgeeks.org/node-js-response-writecontinue-method/)

***response . write Continue()***(*在 v0.3.0* 中添加)方法是一个内置的 *http* 模块的应用编程接口，它向客户端发送一个 *HTTP/1.1 100* Continue 消息，指示请求体应该被发送。请参见服务器上的“*检查继续*”事件。即使没有连接侦听器，也会在内部调用*response . write continue()*。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

**进口:**

```
const http = require('http');

```

**语法:**

```
response.writeContinue();

```

**参数:**此方法不接受任何参数。

**返回值:**不返回值，而是向客户端发送 *HTTP/1.1 100* Continue 消息，表示请求正文应该发送。

下面的例子说明了 Node.js 中 *response.writeContinue()* 方法的使用

**例 1:** 程序无*响应. writeContinue()* 方法。

**文件名:index.js**

```
// Node.js program to demonstrate the 
// response.writeContinue() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(function(request, response){

  // Writing string data
  response.write("Heyy geeksforgeeks ", 'utf8', () => {
      console.log("Writing Data...");
  });

  // Defining Buffer 'Hello world'
  const buf = Buffer.alloc(11, 'aGVsbG8gd29ybGQ=', 'base64');

  // Writing the buffer data.
  response.write(buf, 'utf8', () => {
     console.log("Writing Buffer Data...");
  });

  // Prints Output on the browser in response
  response.end(' ok');
});

// Listening to http Server
httpServer.listen(PORT, () => {
   console.log("Server is running at port 3000...");
});
```

**输出:**

> **输出:**控制台内
> 
> 服务器正在端口 3000 上运行…
> 
> 正在写入数据…
> 
> 正在写入缓冲区数据…

现在在浏览器中运行 *http://localhost:3000/* 。

> **输出:**浏览器内
> 
> heyy geeksforgeeks 你好世界好吗

**例 2:** 使用***response . write continue()*方法。**

****文件名:index.js****

```
// Node.js program to demonstrate the 
// response.writeContinue() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(function(request, response){

  // Writing string data
  response.write("Heyy geeksforgeeks ", 'utf8', () => {
      console.log("Writing Data...");  
  });

  // Using response.writeContinue() method
  response.writeContinue();

  // Defining Buffer 'Hello world'
  const buf = Buffer.alloc(11, 'aGVsbG8gd29ybGQ=', 'base64');

  // Writing the buffer data.
  response.write(buf, 'utf8', () => {
      console.log("Writing Buffer Data...");
  });

  // Prints Output on the browser in response
  response.end(' ok');
});

// Listening to http Server
httpServer.listen(PORT, () => {
   console.log("Server is running at port 3000...");
});
```

**使用以下命令运行 **index.js** 文件:**

```
node index.js
```

****输出:****

> ****输出:**控制台内**
> 
> **服务器正在端口 3000 上运行…**
> 
> **正在写入数据…**
> 
> **正在写入缓冲区数据…**

****参考:**[https://nodejs . org/API/http . html # http _ response _ write continue](https://nodejs.org/api/http.html#http_response_writecontinue)**