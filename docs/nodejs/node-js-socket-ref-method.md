# Node.js socket.ref()方法

> 原文:[https://www.geeksforgeeks.org/node-js-socket-ref-method/](https://www.geeksforgeeks.org/node-js-socket-ref-method/)

**socket.ref()** 方法是 dgram 模块内 socket 类的内置应用编程接口，用于获取包含其中所有信息的特定 Socket 的引用。

**语法:**

```
const socket.ref()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回包含所有信息的特定套接字的引用。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// server.ref() method

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

        // Getting the reference of the server
        // by using ref() method
        const size = server.ref();

        // Display the result
        console.log(size.eventNames());

    });

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
[ 'message' ]
UDP String: Hello
```

**示例 2:** **文件名:index . js**

## JavaScript

```
// Node.js program to demonstrate the
// server.ref() method

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
server.on('listening', ()=> {

    // Getting address information
    // for the server
    const address = server.address();

    // display the result
    console.log(`server listening
        ${address.address}: $ { address.port }`);
});

// Binding server with port address
// by using bind() method
server.bind(1234, ()=> {

    // Getting the reference of server
    // by using ref() method
    const size = server.ref();

    // Display the result
    console.log(size.eventNames());
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
server listening 0.0.0.0:1234
[ 'message', 'listening' ]
UDP String: Hello
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:https:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ ref](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_ref)