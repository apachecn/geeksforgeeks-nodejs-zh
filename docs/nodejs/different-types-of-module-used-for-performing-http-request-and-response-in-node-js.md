# 用于在 Node.js

中执行 HTTP 请求和响应的不同类型的模块

> 原文:[https://www . geesforgeks . org/不同类型的模块-用于在节点中执行 http 请求和响应-js/](https://www.geeksforgeeks.org/different-types-of-module-used-for-performing-http-request-and-response-in-node-js/)

HTTP 的请求和响应是万维网的主要基本模块。在 [Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 中执行 HTTP 请求和响应的方法有很多。各种开源库也可用于执行任何类型的 HTTP 请求和响应。

HTTP 请求意味着要么从指定的 URI 检索数据，要么将数据推送到服务器。在服务器和客户端之间，它作为请求-响应协议工作。客户端可以是网络浏览器，服务器可以是托管网站的计算机系统上的应用程序。

下面讨论了创建不同帖子请求的三种方法:

1.  使用 HTTP 模块
2.  使用 express.js 框架
3.  使用公理模块

[**HTTP 模块:**](https://www.geeksforgeeks.org/node-js-http-module/)HTTP 模块是内置模块，无需外部安装命令即可使用。

**导入模块:**

```js
const http = require("http")
```

**文件名:index.js**

## java 描述语言

```js
// Importing http module
const http = require("http")

// Creating http server
const server=http.createServer((req,res) => {

    // Handling the request
    if(req.url == '/') {

      // Sending the response
      res.write("<h1>This is the server GFG!<h1>")
      res.statusCode = 200

      // Ending the response
      res.end()
    }
})

// Listening the server
server.listen((3000),() => {
   console.log("Server is Running")
})
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

![](img/eafee49cdd1f9096f185933191252aea.png)

现在打开浏览器，转到***http://localhost:3000***可以看到如下输出:

![](img/fb16f0e16fb98f38f8214355b92d7a67.png)

[**Express.js 框架:**](https://www.geeksforgeeks.org/working-of-express-js-middleware-and-its-benefits/) Express.js 是需要使用 npm install 命令从外部安装的第三方模块。Express.js 是 Node.js 的强大框架之一，它可以借助不同的中间件处理不同类型的客户端请求。

**安装模块:**使用以下命令安装模块:

```js
npm install express.js
```

**文件名:index.js**

## java 描述语言

```js
// Requiring module
const express = require("express");

// Creating express app object
const app = express();

// Handling '/' route
app.get("/", (req, res, next) => {

  // Sending the response
  res.send("unknown request");
})

// Handling '/GFG' route    
app.get("/GFG", (req, res, next) => {

  // Sending the response
  res.send("Getting request of GFG");
})

// Handling '/Hello' route
app.get("/Hello", (req, res, next) => {

  // Sending the response
  res.send("Getting request of the Hello");
})

// Server setup
app.listen(3000, () => {
  console.log("Server is Running");
})
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Server is Running
```

现在打开浏览器，转到***http://localhost:3000/GFG***可以看到如下输出:

![](img/076187f5b3af4591b4736610165cc248.png)

**Axios 模块:**另一个可以使用的库是 **Axios** 。这是一个流行的 node.js 模块，用于执行 HTTP 请求，支持所有最新的浏览器。它还支持异步/等待语法来执行开机自检请求。

**安装模块:**使用以下命令安装模块:

```js
npm install axios
```

**文件名:index.js**

## java 描述语言

```js
// Importing the axios module
const axios = require('axios');

// Data to be sent
const data = {
    name: 'geeksforgeeks',
    job: 'Content Writer',
    topic: 'Node.js'
};

const addUser = async () => {
    try {

      // Endpoint of resource
      var URL = 'https://reqres.in/api/usersdata'

      // Making post request
      const res = await axios.post(URL, data);

      // Printing the response data
      console.log('Body: ', res.data);  
    } catch (err) {
      // Printing the error
      console.error(err.Message);
    }
};
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

![](img/8e2c5e193cf96ba2e19fe711e9a97790.png)