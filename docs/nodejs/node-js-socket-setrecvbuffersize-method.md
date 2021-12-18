# node . js socket . setrecvbbuffersize()方法

> 原文:[https://www . geesforgeks . org/node-js-socket-setrecvbuffersize-method/](https://www.geeksforgeeks.org/node-js-socket-setrecvbuffersize-method/)

socket.setRecvBufferSize()方法是 dgram 模块中 socket 类的内置应用程序编程接口，用于以字节为单位设置 Socket 接收缓冲区的大小。

**语法:**

```
const socket.setSendBufferSize( size )
```

**参数:**该方法将整数值大小作为大小分配的参数。

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// server.getRecvBufferSize() method

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

        // Setting the receiver buffer size
        // by using setRecvBufferSize() method
        server.setRecvBufferSize(12345);

        // Getting the receiver buffer size
        // by using getRecvBufferSize() method
        const size = server.getRecvBufferSize();

        // Display the result
        console.log(size);

    });

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
12345
UDP String: Hello
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// server.setRecvBufferSize() method

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

    // Getting address information for
    // the server
    const address = server.address();

    // Display the result
    console.log(`server listening
    ${address.address}:${address.port}`);

});

// Binding server with port address
// by using bind() method
server.bind(1234, () => {

    // Setting the receive buffer size
    // by using setRecvBufferSize() method
    server.setRecvBufferSize(1234567);

    // Getting the receive buffer size
    // by using getRecvBufferSize() method
    const size = server.getRecvBufferSize();

    // Display the result
    console.log(size);

});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
server listening 0.0.0.0:1234
1234567
UDP String: Hello
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ setrecvbuffersize _ size](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_setrecvbuffersize_size)