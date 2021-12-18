# Node.js socket.address()方法

> 原文:[https://www . geesforgeks . org/node-js-socket-address-method/](https://www.geeksforgeeks.org/node-js-socket-address-method/)

**socket.address()** 方法是 dgram 模块中 socket 类的内置应用编程接口，用于获取包含套接字地址信息的对象。

**语法:**

```
const socket.address()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回包含套接字地址信息的对象。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// server.address() method

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
}).bind(1234, () => {

    // Getting the address information for
    // the server by using address() method
    const address = server.address()

    // Display the result
    console.log(address);
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
{ address: '0.0.0.0', family: 'IPv4', port: 1234 }
UDP String: Hello
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// server.address() method

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
server.bind(1234, () => {

    // Adding a multicast address for others to join
    server.addMembership('224.0.0.114');
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

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ address](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_address)