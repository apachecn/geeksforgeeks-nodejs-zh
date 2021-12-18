# Node.js socket.send()方法

> 原文:[https://www.geeksforgeeks.org/node-js-socket-send-method/](https://www.geeksforgeeks.org/node-js-socket-send-method/)

**socket.send()** 方法是 dgram 模块内 socket 类的内置应用编程接口，用于将消息从一个 socket 发送到另一个 Socket。

**语法:**

```
socket.send(msg[, offset, length][, port][, address][, callback])
```

**参数:**该方法取以下参数:

*   **msg:** message to be sent.
*   **Offset:** The offset in the buffer where the message starts.
*   **Length:** The number of bytes in the message.
*   **Port:** Destination port.
*   **Address:** The name or IP address of the destination host.
*   **Callback:** Called after the message is sent.

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// server.send() method

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
// by using send() method
client.send("Hello", 0, 7, 1234, "localhost");
```

**输出:**

```
[ 'message' ]
UDP String: Hello
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// server.send() method

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
  console.log(
`server listening ${address.address}:${address.port}`);
});

// Binding server with port address
// by using bind() method
server.bind(1234, () => {

  // Getting the reference of server
  // by using ref() method
  const size = server.ref();

  // display the result
  console.log(size.eventNames());
});

// Client sending message to server
// by using send() method
client.send("Hello", 0, 7, 1234, "localhost", (err) =>{

  if(err) throw err;
  console.log("message sent");
});
```

**输出:**

```
server listening 0.0.0.0:1234
[ 'message', 'listening' ]
message sent
UDP String: Hello
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[**https://nodejs . org/dist/latest-v 12 . x/docs/API/dgram . html # dgram _ socket _ send _ msg _ offset _ length _ port _ address _ callback**](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_send_msg_offset_length_port_address_callback)