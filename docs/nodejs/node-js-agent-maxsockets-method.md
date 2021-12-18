# Node.js agent.maxSockets 方法

> 原文:[https://www . geesforgeks . org/node-js-agent-max sockets-method/](https://www.geeksforgeeks.org/node-js-agent-maxsockets-method/)

**Node.js** HTTP API 是低级的，因此可以支持 HTTP 应用程序。为了访问和使用 HTTP 服务器和客户端，我们需要调用它们(通过'*require(' HTTP '*')。HTTP 消息头表示为 JSON 格式。

***代理. maxSockets*** ( *在 v0.3.6* 中添加)方法是一个内置的应用程序编程接口，它决定了代理每个源可以打开多少个并发套接字。Origin 是 *agent.getName()* 的返回值。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

**进口:**T0】

**语法:**

```
agent.maxSockets;

```

**参数:**该功能不接受上述任何参数。

**返回值** < *号* >:默认设置为无穷大。它决定了代理可以为每个源打开多少个并发套接字。

下面的例子说明了 Node.js 中 *agent.maxSockets* 方法的使用

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// agent.maxSockets method 

// Importing http module 
const http = require('http');

// Importing agentkeepalive module 
const Agent = require('agentkeepalive'); 

// Creating new agent 
const keepAliveAgent = new Agent({}); 

console.log(keepAliveAgent.maxSockets);

// Options object 
const options = { 
  host: 'geeksforgeeks.org', 
  port: 80, 
  path: '/', 
  method: 'GET', 
  agent: keepAliveAgent, 
}; 

// Requesting via http server module 
const req = http.request(options, (res) => { 
  // Printing statuscode 
  console.log("StatusCode: ", res.statusCode); 
}); 

req.end(); 
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

> **输出:**
> 
> Infinity
> 
> 状态代码:301

**参考:**[https://nodejs . org/API/http . html # http _ agent _ maxsockets](https://nodejs.org/api/http.html#http_agent_maxsockets)