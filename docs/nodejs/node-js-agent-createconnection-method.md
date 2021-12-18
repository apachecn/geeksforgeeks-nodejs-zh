# node . js agent . createconnection()方法

> 原文:[https://www . geesforgeks . org/node-js-agent-create connection-method/](https://www.geeksforgeeks.org/node-js-agent-createconnection-method/)

Node.js HTTP API 是低级的，因此它可以支持 HTTP 应用程序。为了访问和使用 HTTP 服务器和客户端，我们需要调用它们(通过“require”(“HTTP”))。HTTP 消息头表示为 JSON 格式。

**agent . createconnection()**(*在 v0.11.4* 中添加)方法是一个内置的“Http*”*模块的应用编程接口，用于生成套接字或流，进一步用于 *HTTP* 请求，默认情况下与 *net.createConnection()* 完全相同。它返回一个< *网的实例。Socket* >类，是< *流的子类。双工* >。可以通过从该函数返回套接字/流或将套接字/流传递给回调来提供套接字或流。

**语法:**

```js
agent.createConnection(options[, callback])

```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **选项** < *对象* > **:** 是任何包含连接细节的<对象>或 JSON 数据。

*   **回调** < *函数* > **:是一个回调<函数>接收创建的套接字。**

**返回值** <流。双工>:返回可读可写的*双工流*。

下面的例子说明了在 Node.js 中使用*代理. createConnection(选项[，回调])* 方法。

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// agent.createConnection() method 

// Importing http module
const http = require('http');

// Creating new agent
var agent = new http.Agent({});

// Creating new connection
var createConnection = agent.createConnection;
console.log('Connection successfully created...');

// Printing that connection
console.log('Connection: ', createConnection);
```

**输出:**

```js
Connection successfully created...
Connection: [Function: connect]

```

**示例 2:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// agent.createConnection() method 

// Importing http module
const http = require('http');
var agent = new http.Agent({});

// Creating new agent
const aliveAgent = new http.Agent({
    keepAlive: true,
    maxSockets: 0, maxSockets: 5,
});

// Creating new agent
var agent = new http.Agent({});

// Creating new connection
var createConnection = aliveAgent.createConnection;

// Creating new connection
var createConnection = agent.createConnection;
console.log('Connection successfully created...');

// Printing the connection
console.log(createConnection);
console.log('Connection successfully created...');

// Printing the connection
console.log('Connection: ', createConnection);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

```js
Connection successfully created...
Connection: [Function: connect]
Connection successfully created...
Connection: [Function: connect]

```

**参考:**[https://nodejs . org/API/http . html # http _ agent _ create connection _ options _ callback](https://nodejs.org/api/http.html#http_agent_createconnection_options_callback)