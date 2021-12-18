# Node.js socket.remoteAddress()方法

> 原文:[https://www . geesforgeks . org/node-js-socket-remote address-method/](https://www.geeksforgeeks.org/node-js-socket-remoteaddress-method/)

**socket.remoteAddress()** 方法是 dgram 模块内 socket 类的内置应用编程接口，用于获取包含端口、地址和家族的服务器远程地址。

**语法:**

```js
const socket.remoteAddress()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回包含端口、地址和家族的服务器远程地址。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// server.remoteAddress() method

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Catching the message event
server.on("message", function (msg) {

    // Displaying the client message
    process.stdout.write("UDP String: " + msg + "\n");

    // Exiting process
    process.exit();

});

// Catching the listening event
server.on('listening', () => {

    // Getting address information for the server
    const address = server.address();

    // Display the result
    console.log(`server listening
        ${address.address}:${address.port}`);

});

// Binding server with port address
// by using bind() method
server.bind(1234, () => {

    // Connecting server with the port
    // and local host
    server.connect(1234, "localhost", () => {
        console.log("connected");

        // Getting remote address of server
        // by using remoteAddress() method
        const add = server.remoteAddress();

        // Display the result
        console.log(add);
    });
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```js
server listening 0.0.0.0:1234
connected
{ address: '127.0.0.1', family: 'IPv4', port: 1234 }
```

**例 2:如果服务器未连接。**

**文件名:index . js**

## 【JavaScript】

```js
// Node.js program to demonstrate the
// server.remoteAddress() method

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Catching the message event
server.on("message", function (msg) {

    // Displaying the client message
    process.stdout.write("UDP String: " + msg + "\n");

    // Exiting process
    process.exit();
});

// Catching the listening event
server.on('listening', () => {

    // Getting address information for the server
    const address = server.address();

    // Display the result
    console.log(`server listening
        ${address.address}:${address.port}`);
});

// Binding server with port address
// by using bind() method
server.bind(1234, () => {

    // Getting remote address of server
    // by using remoteAddress() method
    // it will throw error
    const add = server.remoteAddress();

    // Display the result
    console.log(add);
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```js
node GFG.js
server listening 0.0.0.0:1234
dgram.js:745
    throw new ERR_SOCKET_DGRAM_NOT_CONNECTED();
    ^

Error [ERR_SOCKET_DGRAM_NOT_CONNECTED]: Not connected
    at Socket.remoteAddress (dgram.js:745:11)
    at Socket.<anonymous> (F:\java\GFG.js:42:28)
    at Socket.onListening (dgram.js:225:10)
    at Socket.emit (events.js:327:22)
    at startListening (dgram.js:150:10)
    at dgram.js:345:7
    at processTicksAndRejections (internal/process/task_queues.js:85:21) {
  code: 'ERR_SOCKET_DGRAM_NOT_CONNECTED'
}
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ remote address](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_remoteaddress)