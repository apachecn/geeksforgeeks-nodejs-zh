# Node.js dgram.createSocket()方法

> 原文:[https://www . geesforgeks . org/node-js-dgram-create socket-method/](https://www.geeksforgeeks.org/node-js-dgram-createsocket-method/)

方法是 dgram 模块中内置的应用程序编程接口，用于创建 dgram.socket 对象。

**语法:**

```js
const dgram.createSocket(options[, callback])
```

**参数:**该方法取以下参数:

*   **Option:** One of the following options will be used-
    *   **Type:** series socket.
    *   **Boolean value when reusing address:** .
    *   **ipv6Only:** Setting IPv6 only to true will disable dual stack support.
    *   **recvbbuffersize:** 沙吾提 S7-1200 可编程控制器哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟哟。
    *   【T0 发送缓冲区大小】so _ snd 缓冲区.
    *   **Search:** User-defined search function.
*   **Callback:** Callback function for further operation.

**返回值:**这个方法返回 dgram.socket 的对象。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// dgram.createSocket() method

// importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket by using
// createSocket() method
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

        // Setting the Send buffer size
        // by using setSendBufferSize() method
        server.setSendBufferSize(12345);

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

```js
12345
UDP String: Hello
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// dgram.createSocket() method

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket by using
// createSocket() method
var client = dgram.createSocket("udp4", () => {
    console.log("client is created");
});
var server = dgram.createSocket("udp4", () => {
    console.log("server is created");
});

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

    // Setting the Send buffer size
    // by using setSendBufferSize() method
    server.setSendBufferSize(1234567);

    // Getting the Send buffer size
    // by using getSendBufferSize() method
    const size = server.getSendBufferSize();

    // Display the result
    console.log(size);
});

// Client sending message to server
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```js
server listening 0.0.0.0:1234
1234567
server is created
UDP String: Hello
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ dgram _ create socket _ options _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_dgram_createsocket_options_callback)