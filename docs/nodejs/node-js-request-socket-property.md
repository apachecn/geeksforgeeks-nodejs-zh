# Node.js request.socket 属性

> 原文:[https://www . geesforgeks . org/node-js-request-socket-property/](https://www.geeksforgeeks.org/node-js-request-socket-property/)

***request . socket***(*在 v0.3.0 中添加)*属性是 *http* 模块的一个内置属性，该模块引用了底层套接字，大多数用户无法访问该属性。具体来说，套接字不发出可读的事件，但是可以通过请求连接访问套接字。这个属性保证是< *网的一个实例。Socket* >类，<流的一个子类。双工>。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

```
const http = require('http'); 
```

**语法:**

```
request.socket

```

**参数:**该属性不接受任何参数。

**返回值:**它以对象的形式返回请求数据，该对象包含大量与套接字相关的数据。

*   <*小溪。复式* > : < *溪流。双工* >或双工流是实现可读和可写的流。

下面的例子说明了 *request.socket* 属性在 Node.js 中的使用

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// req.socket property 

// Using require to access http module 
const http = require('http');

// Requesting from google server
const req = http.get({ host: 'www.geeksforgeeks.org' });

// Ending the request
req.end();

req.once('response', (res) => {

    // Printing socket after getting response
    console.log(req.socket);

    // Printing address and port after
    // getting response
    console.log(`IP address of geeksforgeeks is 
            ${req.socket.localAddress}.`);

    console.log(`Its Port is ${req.socket.localPort}.`);
});
```

**输出:**

> > > <ref>Socket{ connecting: false，</ref>
> 
> _hadError： 假，
> 
> _parent: null，
> 
> _ host:' www . geeeksforgeks . org '……[Symbol(kBytesWritten)]:0 }
> 
> > > IP 地址为 192.168.43.207
> 
> >>它的端口是 56933。

**示例 2:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// req.socket property 

// Using require to access http module 
const { get } = require('http');

// Setting host server url
const options = { host: 'www.geeksforgeeks.org' };

// Requesting from geeksforgeeks server
const req = get(options);
req.end();

req.once('response', (res) => {

    // Printing the requestrelated data
    console.log("Status:", res.statusCode, 
                        res.statusMessage);

    console.log("Host:", req.socket._host);

    console.log("Method:", 
        req.socket.parser.outgoing.method);

    console.log("Parser Header:", 
            req.socket.parser.outgoing._header);

    console.log("Writable:", req.socket.writable);
    console.log("Readable:", req.socket.readable);

    console.log("Http Header:", 
            req.socket._httpMessage._header);

    if (req.socket._httpMessage._header === 
            req.socket.parser.outgoing._header) {
        console.log("Both headers are exactly same...")
    } else {
        console.log("Headers are not same...")
    }

    // Printing address and port after
    // getting response
    console.log(`IP address of geeksforgeeks is 
        ${req.socket.localAddress}.`);

    console.log(`Its port is ${req.socket.localPort}.`);
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

**输出:**

> >>状态:301 永久移动
> 
> >>主持人:www.geeksforgeeks.org
> 
> >>方法:获取
> 
> >>解析器头:GET / HTTP/1.1
> 
> 主持人:www.geeksforgeeks.org
> 
> 连接:关闭
> 
> >>可写:真
> 
> >>可读:真
> 
> > > Http 头:GET / HTTP/1.1
> 
> 主持人:www.geeksforgeeks.org
> 
> 连接:关闭
> 
> >>两个标题完全相同…
> 
> > > IP 地址为 192.168.43.207
> 
> >>它的端口是 57425。

**参考:**T2】https://nodejs.org/api/http.html#http_request_socket