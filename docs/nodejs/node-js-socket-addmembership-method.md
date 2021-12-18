# Node.js socket.addMembership()方法

> 原文:[https://www . geesforgeks . org/node-js-socket-add membership-method/](https://www.geeksforgeeks.org/node-js-socket-addmembership-method/)

**socket.addMembership()** 方法是 dgram 模块中 socket 类的内置应用编程接口，用于使内核在特定的组播地址加入组播组。

**语法:**

```js
const socket.addMembership(multicastAddress[, multicastInterface])
```

**参数:**该方法以表示组播地址的字符串作为参数。

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// server.addMembership() method

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
    .bind(1234, () => {

        // Adding a multicast address for
        // others to join
        server.addMembership('224.0.0.114');
    });

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```js
UDP String: Hello
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// server.addMembership() method

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

    // Adding a multicast address for others to join
    server.addMembership('224.0.0.114');
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```js
server listening 0.0.0.0:1234
UDP String: Hello
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ addmembership _ multicast address _ multicast interface](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_addmembership_multicastaddress_multicastinterface)