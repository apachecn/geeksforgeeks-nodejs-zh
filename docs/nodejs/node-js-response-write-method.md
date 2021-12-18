# Node.js response.write()方法

> 原文:[https://www . geesforgeks . org/node-js-response-write-method/](https://www.geeksforgeeks.org/node-js-response-write-method/)

***response . write()***(*在 v0.1.29* 中添加)方法是一个内置的应用程序接口的“ *http* ”模块，当请求是一个 *HEAD* 请求时，它发送一大块被省略的响应体。如果调用了这个方法，而 *response.writeHead()* 还没有被调用，它将切换到隐式头模式，并刷新隐式头。

第一次调用 *response.write()* 时，它会将缓冲的头信息和正文的第一个块发送给客户端。第二次调用 *response.write()* 时，Node.js 假设数据将被流式传输，并单独发送新数据。也就是说，响应被缓冲到主体的第一个块。区块可以是字符串或缓冲区。如果块是字符串，第二个参数指定如何将其编码到字节流中。当这个数据块被刷新时，回调将被调用。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

**进口:**

```
const http = require('http');

```

**语法:**

```
response.write(chunk[, encoding][, callback]);

```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **组块** < *字符串* > | < *缓冲区* > **:** 它接受任何缓冲区或字符串数据。
*   **编码** < *字符串* > **:** 默认编码设置为“ *utf8* ”。它接受字符串数据。
*   **回拨** < *功能* > **:接受回拨功能。**

**返回值** < *布尔* > **:** 如果整个数据被成功刷新到内核缓冲区，则返回*真*，如果全部或部分数据在用户内存中排队，则返回*假*。当缓冲器再次空闲时，将发出“*排放*”。

下面的例子说明了 Node.js 中 *response.write()* 属性的使用

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// response.write() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(function(request, response){

  // Writing string data
  response.write("Heyy geeksforgeeks ", 'utf8', () => {
      console.log("Writing string Data...");
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
> 正在写入字符串数据…

**现在在浏览器中运行 http://localhost:3000/即可。**

> **输出:**浏览器内
> 
> heyy geeksforgeeks 好的

**示例 2:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// response.write() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(function(request, response){

  var str = "GeeksForGeeks wishes you a warm welcome...";

  // Writing string data with
  // 16-bit Unicode Transformation Format
  response.write(str, 'utf16', () => {
     console.log("Writing string Data...");
  });

  // Allocating predefined Buffer 'Hello world'
  const buf = Buffer.alloc(11, 'aGVsbG8gd29ybGQ=', 'base64');

  // Writing the buffer data.
  response.write(buf, 'utf8', () => {
     console.log("Writing Buffer Data...");
  });

  // Creating buffer
  const buff = Buffer.from(' hello world', 'utf8');

  // Writing the buffer data.
  response.write(buff, 'utf8', () => {
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

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> **输出:**控制台内
> 
> 服务器正在端口 3000 上运行…
> 
> 正在写入字符串数据…
> 
> 正在写入缓冲区数据…
> 
> 正在写入缓冲区数据…

现在在浏览器中运行***http://localhost:3000/***。

> **输出:**浏览器内
> 
> GeeksForGeeks 祝你热烈欢迎…你好世界你好世界好

**参考:**[https://nodejs . org/API/http . html # http _ response _ write _ chunk _ encoding _ callback](https://nodejs.org/api/http.html#http_response_write_chunk_encoding_callback)