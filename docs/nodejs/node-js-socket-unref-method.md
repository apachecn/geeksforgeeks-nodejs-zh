# Node.js socket.unref()方法

> 原文:[https://www.geeksforgeeks.org/node-js-socket-unref-method/](https://www.geeksforgeeks.org/node-js-socket-unref-method/)

**socket.unref()** 方法是 dgram 模块中 socket 类的内置应用编程接口，用于允许进程退出，即使套接字仍在侦听。

**语法:**

```js
const socket.unref()
```

**参数:**此方法不接受任何参数。

**返回值:**这个方法返回包含所有信息的特定套接字的引用。

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the
// server.unref() property

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Handling the message event
server.on("message", function (msg) {

    // Displaying the client message
    process.stdout.write("UDP String: " 
                    + msg + "\n");

    // Exiting process
    process.exit();

})// Binding server with port
    .bind(1234, () => {

        // Getting the reference of the server
        // by using unref() method
        const size = server.unref();

        // Display the result
        console.log(size.eventNames());
    });

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```js
[ 'message' ]
UDP String: Hello
```

**示例 2:** **文件名:**

```js
// Node.js program to demonstrate the
// server.unref() method

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Handling the message event
server.on("message", function (msg) {

    // Displaying the client message  
    process.stdout.write("UDP String: "
            + msg + "\n");

    // Exiting process 
    process.exit();
});

// Handling the listening event
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

    // Getting the reference of server
    // by using unref() methods
    const size = server.unref();

    // Display the result
    console.log(size.eventNames());
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
server listening 0.0.0.0:1234
[ 'message', 'listening' ]
UDP String: Hello
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ unref](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_unref)