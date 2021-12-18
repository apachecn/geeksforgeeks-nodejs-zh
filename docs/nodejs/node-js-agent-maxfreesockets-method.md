# Node.js agent.maxFreeSockets 方法

> 原文:[https://www . geesforgeks . org/node-js-agent-maxfreesockets-method/](https://www.geeksforgeeks.org/node-js-agent-maxfreesockets-method/)

Node.js *HTTP* *API* 是低级的，因此它可以支持 *HTTP* 应用程序。为了访问和使用 HTTP 服务器和客户端，我们需要调用它们(通过'*require(' HTTP '*')。HTTP 消息头表示为 JSON 格式。

***agent . maxfreesockets***(*在 v0.11.7* 中添加)方法是一个内置的“Http”模块的应用程序编程接口，它设置了在空闲状态下将保持打开的最大套接字数量。

为了得到响应和正确的结果，我们需要导入‘http’模块。

**进口:**

```
const http = require('http');

```

**语法:**

```
agent.maxFreeSockets;

```

**参数:**该功能不接受上述任何参数。

**返回值** < *号* > **:默认设置为 256。对于启用了 keepAlive 的代理，这将设置在空闲状态下保持打开的最大套接字数量。**

下面的例子说明了 Node.js 中 *agent.maxFreeSockets* 方法的使用

**示例 1:Filename:index . js**

```
// Node.js program to demonstrate the 
// agent.maxFreeSockets method 

// Importing http module 
const http = require('http'); 

// Importing agentkeepalive module 
const Agent = require('agentkeepalive'); 

// Creating new agent 
const keepAliveAgent = new Agent({}); 

console.log(keepAliveAgent.maxFreeSockets);

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

**输出:**

> 256
> 
> 状态代码:301

**参考:**[https://nodejs . org/API/http . html # http _ agent _ maxfreeskets](https://nodejs.org/api/http.html#http_agent_maxfreesockets)