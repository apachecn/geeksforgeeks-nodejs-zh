# Node.js http。ClientRequest.setTimeout()方法

> 原文:[https://www . geesforgeks . org/node-js-http-client request-settimeout-method/](https://www.geeksforgeeks.org/node-js-http-clientrequest-settimeout-method/)

**http。ClientRequest.setTimeout()** 是 HTTP 模块内 ClientRequest 类的内置应用编程接口，用于设置客户端请求的请求超时。

**语法:**

```js
request.setTimeout(timeout[, callback])
```

**参数:**该方法以超时值为参数，单位为毫秒，第二个参数是给定超时值后执行的回调函数。

**返回值:**这个方法只返回一个回调函数做进一步操作。

**示例 1: Filename-index.js**

## java 描述语言

```js
// Node.js program to demonstrate the 
// request.setTimeout() method

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

    // Setting the timeout for the client request
    // by using host method
    req.setTimeout(3000, () => {
        console.log("timeout")
        process.exit(0)
    })
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
timeout
```

**示例 2: Filename-index.js**

## 【JavaScript】

```js
// Node.js program to demonstrate the 
// request.setTimeout() method

// Importing http module
const http = require('http');

// Create an HTTP server
http.createServer((req, res) => { }).listen(3000, '127.0.0.1', () => {

    // Getting client request
    const req = http.request({
        port: 3000,
        host: '127.0.0.1',
    });

    // Setting the timeout for the client request
    // by using host method
    req.setTimeout(5000, () => {
        console.log("timeout")
        process.exit(0)
    })
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
timeout
```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/http . html # http _ request _ settimeout _ time out _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/http.html#http_request_settimeout_timeout_callback)