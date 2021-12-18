# express . js vs KoaJS in node . js

> 原文:[https://www . geesforgeks . org/express-js-vs-koajs-in-node-js/](https://www.geeksforgeeks.org/express-js-vs-koajs-in-node-js/)

**Node.js:** Node.js 是一个开源的跨平台运行时环境，用于在浏览器外执行 JavaScript 代码。你需要记住 NodeJS 不是一个框架，也不是一种编程语言。大多数人都很困惑，明白这是一个框架或者一种编程语言。我们经常使用 Node.js 来构建后端服务，比如像 Web App 或者移动 App 这样的 API。

**快递模块:**为了使用快递模块，我们需要安装 **NPM** ( *节点包管理器*)和以下模块(*在 cmd* 上)。

```
// Creates package.json file
>> npm init 

// Installs express module
>> npm install express --save // OR
>> npm i express -s  

```

**导入快递模块:**导入快递模块，将返回的实例存储到变量中。

**语法:**

```
var express = require("express");

```

**创建服务器:**上面的语法调用“ *express()* ”函数，并创建一个新的 express 应用程序，该应用程序存储在 app 变量中。

**语法:**

```
// Importing and creating express application
const app = express();  
var express = require("express")(); // OR

```

**发送和侦听响应:**它与客户端和服务器通信请求和响应。它需要 PORT < *号* >和 IP < *号* >进行通信。

```
app.listen(PORT, IP, Callback);

```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **PORT**<*Number*>:端口是通信的端点，有助于与客户端和服务器进行通信。

*   **IP** < *编号*>:IP 代表主机或设备的 IPv4 或 IPv6 地址。

*   **回调** < *函数* >:它接受一个函数。

下面的例子说明了 Node.js 中的 *Express.js* 模块

**示例 1:** **文件名:index.js**

```
// Node.js program to create server  
// with help of Express module

// Importing express  
const express = require('express');

// Creating new express app  
const app = express();

// PORT configuration
const PORT = process.env.PORT || 2020;

// IP configuration
const IP = process.env.IP || 2021;

// Create a route for the app
app.get('/', (req, res) => {
 res.send('Hello Vikas_g from geeksforgeeks!');
});

// Create a route for the app
app.get('*', (req, res) => {
 res.send('OOPS!! The link is broken...');
});

// Server listening to requests
app.listen(PORT, IP, () => {
 console.log(`The Server is running
     at: http://localhost:${PORT}/`);
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

**输出:**

> 服务器运行于:http://localhost:2020

现在在网页浏览器中输入 *http://127.0.0.1:2020/* 或 *http://localhost:2020/* 查看输出。

**KoaJS 模块:**为了使用 **KoaJS** 模块，我们需要安装 **NPM** ( *节点包管理器*)和以下模块(在 cmd 上)。

```
// Creates package.json file
>> npm init

// Installs koa module<
>> npm install koa --save 
>> npm i koa -s  // OR

```

**导入 KoaJS 模块:**导入 *KoaJS* 模块，并将返回的实例存储到变量中。

**语法:**

```
var koa = require("koa"); // Importing koa module

```

**创建服务器:**上面的语法导入 koa 模块，并创建一个新的 koa 应用程序，该应用程序存储在应用程序变量中。

**语法:**

```
const app = new koa();  // Creating koa application

```

**发送和侦听响应:**它与客户端和服务器通信请求和响应。它需要 PORT < *号* >和 IP < *号* >进行通信。

```
app.listen(PORT, IP, Callback);

```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **PORT**<*Number*>:端口是通信的端点，有助于与客户端和服务器进行通信。

*   **IP** < *编号*>:IP 代表主机或设备的 IPv4 或 IPv6 地址。

*   **回调** < *函数* >:它接受一个函数。

下面的例子说明了 Node.js 中的 *KoaJS* 模块

**示例 2:** **文件名:**

```
// Node.js program to create server
// with help of Koa module

// Importing koa module
const koa = require('koa');

// Creating new koa app
const app = new koa();

// PORT configuration
const PORT = process.env.PORT || 2020;

// IP configuration
const IP = process.env.IP || 2021;

app.use(function *() {
this.body = "Hello GeeksForGeeks!";
});

// Server listening to requests
app.listen(PORT, IP, ()=>{
console.log("Server started at port", PORT);
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

**输出:**

> 服务器在端口 2020

运行

现在在网页浏览器中输入 *http://127.0.0.1:2020/* 或 *http://localhost:2020/* 查看输出。