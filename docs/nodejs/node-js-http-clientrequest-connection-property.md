# Node.js http。ClientRequest.connection 属性

> 原文:[https://www . geesforgeks . org/node-js-http-client request-connection-property/](https://www.geeksforgeeks.org/node-js-http-clientrequest-connection-property/)

**http。ClientRequest.connection** 是 HTTP 模块内 ClientRequest 类的内置应用编程接口，用于获取底层客户端请求套接字的引用。

**语法:**

```js
const request.connection
```

**参数:**不接受任何参数作为参数。

**返回值:**不返回值。

**示例 1: Filename-index.js**

## java 描述语言

```js
// Node.js program to demonstrate the 
// request.connection method

// Importing http module
const http = require('http');

// Create an HTTP server
const server = http.createServer((req, res) => {
    res.writeHead(200, { 'Content-Type': 'text/plain' });
    res.end('okay');
});

// Now that server is running
server.listen(3000, '127.0.0.1', () => {

    // Make a request
    const options = {
        port: 3000,
        host: '127.0.0.1',
        headers: {
            'Connection': 'Upgrade',
            'Upgrade': 'websocket'
        }
    };

    // Getting client request
    const req = http.request(options);

    // Getting request socket
    // by using connection method
    const v = req.connection;

    // Display the result
    console.log("request socket :- " + v)

    process.exit(0)
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
request socket :- null
```

**示例 2:Filename-index . js**

## Javascript

```js
// Node.js program to demonstrate the 
// request.connection method

// Importing http module
const http = require('http');

// Create an HTTP server
http.createServer((req, res) => { })
.listen(3000, '127.0.0.1', () => {

    // Getting client request
    const req = http.request({
        port: 3000,
        host: '127.0.0.1',
    });

    // Getting request socket
    // by using connection method
    if (req.connection) {
        console.log("Requested for Connection")
    } else {
        console.log("Not Requested for Connection")
    }

    process.exit(0)
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Not Requested for Connection
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ connection](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_connection)