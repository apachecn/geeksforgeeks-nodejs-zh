# Node.js http.globalAgent 属性

> 原文:[https://www . geesforgeks . org/node-js-http-global agent-property/](https://www.geeksforgeeks.org/node-js-http-globalagent-property/)

***http . global agent***(*在 v0.5.9* 中添加)属性是“http”模块的内置属性，用作所有 HTTP 客户端请求的默认值。它是代理的全局实例。

代理为给定的主机和端口维护一个挂起请求的队列，为每个请求重用一个套接字连接，直到队列为空，此时套接字要么被销毁，要么被放入池中，在池中它被保留以再次用于对同一主机和端口的请求。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

**进口:**

```
const http = require('http');

```

**语法:**

```
http.globalAgent

```

**参数:**该属性不接受上述任何参数。

**返回值** < *http。代理* > **:** 负责管理 HTTP 客户端的连接持久性和重用。

下面的例子说明了*属性在 Node.js 中的使用*

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// http.globalAgent Method

// Importing http module
var http = require('http');
const { globalAgent } = require('http');

const PORT = process.env.PORT || 3000;

console.log(globalAgent);

// Creating http Server
var httpServer = http.createServer(
      function(request, response) {

  console.log(globalAgent);

  var Output = "Hello Geeksforgeeks..., "
    + "Output of global agent is: " +
  JSON.stringify(globalAgent);

  // Prints Output on the browser in response
  response.write(Output);
  response.end('ok');
});

// Listening to http Server
httpServer.listen(PORT, ()=>{
   console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

**输出:**

> 控制台中的
> 
>  **>>服务器正在端口 3000 上运行…
> 
> 代理{ _ 事件:[对象:空原型]{ 0
> 
> 免费:[函数(匿名)]，
> 
> newListener:[函数:mayenablekeylog]}，_eventsCount: 2，
> 
> _ maxlistener:undefined，defaultPort: 80，
> 
> 协议:“http:”，选项:{路径:null }，
> 
> 请求:{}，套接字:{}，
> 
> freeSockets: {}，keepAliveMsecs: 1000，
> 
> keepAlive: false，maxSockets: Infinity，
> 
> maxFreeSockets: 256，调度:“fifo”，
> 
> maxTotalSockets: Infinity，totalSocketCount: 0，
> 
> [符号(kCapture)]: false}**

**现在在浏览器中运行 **http://localhost:3000/** 。**

> ****输出:**在浏览器中**
> 
> **Hello Geeksforgeeks…，全局代理是:{"_events":{}，" _eventsCount":2，" defaultPort":80，**
> 
> **“协议”:“http:“”、“选项”:{“路径”:null}、“请求”:{}、“套接字”:{}，**
> 
> **free sockets:{ }，" keepAliveMsecs":1000，" keepAlive":false，" maxSockets":null，" maxfree xmlsocket ":256，**
> 
> **调度:“fifo”，“maxtotalsockets”:null，“total socket count”:0 }确定**

****参考:**[https://nodejs . org/API/http . html # http _ http _ global agent](https://nodejs.org/api/http.html#http_http_globalagent)**