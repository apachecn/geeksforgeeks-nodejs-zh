# node . js request . writableended 属性

> 原文:[https://www . geesforgeks . org/node-js-request-writableend-property/](https://www.geeksforgeeks.org/node-js-request-writableended-property/)

***request . writableend***(在 v12.9.0 中添加)属性是“ *http* ”模块的内置属性，在调用 *request.end()* 后返回 true。该属性不指示数据是否已被刷新，而是使用 *request.writableFinished* 。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

**语法:**

```
const http = require('http');  

```

**语法:**

```
request.writableEnded 

```

**参数:**该属性不接受任何参数。

**返回值** < *布尔* > **:调用 *request.end()* 后返回 true。**

下面的例子说明了在 Node.js 中 *request.writableEnded* 属性的使用

**示例:** **文件名:**

```
// Node.js program to demonstrate the 
// request.writableEnded property 

// Using require to access http module 
const { get } = require('http'); 

// Setting host server url 
const options = { host: 'www.geeksforgeeks.org' }; 

// Requesting from geeksforgeeks server 
const request = get(options); 

console.log("writableEnded:", request.writableEnded);

request.end(); 

console.log("writableEnded:", request.writableEnded);

request.once('response', (res) => { 

    // Printing the requestrelated data 
    console.log("Status:", res.statusCode, res.statusMessage); 
    console.log("Writable:", request.socket.writable); 
    console.log("Readable:", request.socket.readable); 

    console.log("writableEnded:", request.writableEnded);

    // Printing address and port after getting response 
    console.log(`IP address of geeksforgeeks is`,
    ` ${request.socket.localAddress}.`); 

    console.log(`Its port is ${request.socket.localPort}.`); 
}); 
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

**输出:**

> 可写结束:真
> 
> 可写结束:真
> 
> 状态:301 永久移动
> 
> 可写:真
> 
> 可读:真
> 
> 可写结束:真
> 
> 极客 forgeeks 的 IP 地址为 192.168.43.207。
> 
> 其端口为 64596

**参考:**T2】https://nodejs.org/api/http.html#http_request_writableended