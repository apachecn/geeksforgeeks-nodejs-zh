# node . js socket . setmulticastloopback()方法

> 原文:[https://www . geesforgeks . org/node-js-socket-setmulticastloopback-method/](https://www.geeksforgeeks.org/node-js-socket-setmulticastloopback-method/)

**socket . setmulticast loopback()**方法是 dgram 模块内 Socket 类的内置应用编程接口，用于设置或清除 **IP_MULTICAST_LOOP** socket 选项，帮助服务器在本地接口接收组播数据包。

**语法:**

```
const socket.setBroadcast( flag )
```

**参数:**该方法将布尔值作为参数 true 来启用 **IP_MULTICAST_LOOP** 套接字选项，将布尔值 false 来禁用它。

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// socket.setMulticastLoopback() method

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");
let broadcast_address = 12345;

// Catching the message event
server.on("message", function (msg) {

    // Displaying the client message
    process.stdout.write("UDP String: " + msg + "\n");

    // Exiting process
    process.exit();
})
.bind(broadcast_address, () => {

    // Enable the IP_MULTICAST_LOOP socket option
    // by using the setMulticastLoopback() method
    server.setMulticastLoopback(true);
});

// Client sending message to server
client.send("Hello", 0, 7,
    broadcast_address, "localhost");
```

**输出:**

```
UDP String: Hello
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// socket.setMulticastLoopback() method

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
    const address = server.address();
    console.log(`server listening
        ${address.address}:${address.port}`);
});

// Binding server with port address
server.bind(1234, () => {

    // Enable the IP_MULTICAST_LOOP socket option
    // by using the setMulticastLoopback() method
    server.setMulticastLoopback(true);
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
server listening 0.0.0.0:1234
UDP String: Hello
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ setmulticastloopback _ flag](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_setmulticastloopback_flag)