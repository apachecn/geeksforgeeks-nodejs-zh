# node . js socket . getsendbuffersize()方法

> 原文:[https://www . geesforgeks . org/node-js-socket-getsendbuffersize-method/](https://www.geeksforgeeks.org/node-js-socket-getsendbuffersize-method/)

**socket . getsendbuffersize()**方法是 dgram 模块内 Socket 类的内置应用编程接口，用于获取 Socket 发送缓冲区的大小(以字节为单位)。

**语法:**

```
const socket.getSendBufferSize()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回套接字接收缓冲区的大小，以字节为单位。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// server.getSendBufferSize() method

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
})
    // Binding server with port
    .bind(1234, () => {

        // Getting the send buffer size
        // by using getSendBufferSize() method
        const size = server.getSendBufferSize();

        // Display the result
        console.log(size);

    });

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
65536
UDP String: Hello
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// server.getSendBufferSize() method

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

    // Getting address information
    // for the server
    const address = server.address();

    // Display the result
    console.log(`server listening
    ${address.address}:${address.port}`);

});

// Binding server with port address
// by using bind() method
server.bind(1234, () => {

    // Getting the receive buffer size
    // by using getSendBufferSize() method
    const size = server.getSendBufferSize();

    // Display the result
    console.log(size);
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
server listening 0.0.0.0:1234
65536
UDP String: Hello
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ getsendbuffersize](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_getsendbuffersize)