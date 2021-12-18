# 节点. JS 中 HTTP 请求 vs HapiJS 请求

> 原文:[https://www . geesforgeks . org/http-request-vs-hapi js-request-in-node-js/](https://www.geeksforgeeks.org/http-request-vs-hapijs-request-in-node-js/)

**Node.js:** Node.js 是一个开源的跨平台运行时环境，用于在浏览器外执行 JavaScript 代码。你需要记住 NodeJS 不是一个框架，也不是一种编程语言。大多数人都很困惑，明白这是一个框架或者一种编程语言。我们经常使用 Node.js 来构建后端服务，比如像 Web App 或者移动 App 这样的 API。

**创建和绑定服务器:**使用 *createServer()* 方法创建一个服务器实例，并使用 *listen()* 方法将其绑定到某个端口。

**语法:**

```js
const server = http.createServer().listen(port)

```

**参数:**此方法(listen())接受一个如上所述的参数，如下所述:

*   **Port** < *No.* >: The port is in the range of 1024 to 65535, including registered port and dynamic port.

下面的例子说明了 Node.js 中 *http* 模块的使用

**示例 1:** **文件名:index.js**

```js
// Node.js program to create  
// http server  

// Using require to access http module  
const http = require("http");

// Port number
const PORT = process.env.PORT || 2020;

// Creating server
const server = http.createServer(
  // Server listening on port 2020
  function (req, res) {
     res.write('Hello geeksforgeeks!');  
     // Write a response to the client
     res.end();  
  }
)
.listen(PORT, error => {
  // Prints in console
  console.log(`Server listening on port ${PORT}`)
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

> 服务器监听端口 2020

现在在网页浏览器中输入 *http://127.0.0.1:2020/* 或 *http://localhost:2020/* 查看输出。

**创建服务器:**上面的语法导入了“哈比神”模块，现在它创建了一个服务器。它与客户端和服务器通信请求和响应。需要 PORT <号>和主机<串>进行通信。

**语法:**

```js
const server = Hapi.server({port: 2020, host: 'localhost'});
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **[port]** < *No.* > **:** A port is a communication endpoint that facilitates communication with clients and servers.
*   **主机** < *字符串* > **:** 接受 localhost/127.0.0.1、google.com、geeksforgeeks.org 等主机名。

下面的例子说明了 Node.js 中的 HapiJS 模块

**示例 2:** **文件名:**

```js
// Node.js programe to create server
// using hapi module

// Importing hapi module
const Hapi = require('@hapi/hapi');

// Creating Server
const server = Hapi.server({
   port: 2020,
   host: 'localhost'
});

// Creating route
server.route({
    method: 'GET',
    path: '/',
    handler: (request, hnd) => {
        return 'Hello GeeksForGeeks!';
    }
});

const start = async () => {
  await server.start();
  console.log('Server running at', server.info.uri);
};

process.on('unhandledRejection', (err) => {
  console.log(err);
  process.exit(1);
});
start();
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 服务器运行于:http://localhost:2020

现在在网页浏览器中输入 *http://127.0.0.1:2020/* 或 *http://localhost:2020/* 查看输出。