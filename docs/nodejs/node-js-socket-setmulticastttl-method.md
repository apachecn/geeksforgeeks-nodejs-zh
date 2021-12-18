# node . js socket . setmulticastttl()方法

> 原文:[https://www . geesforgeks . org/node-js-socket-setmulticastttl-method/](https://www.geeksforgeeks.org/node-js-socket-setmulticastttl-method/)

socket.setMulticastTTL()是 dgram 模块中 socket 类的一个内置应用程序编程接口，用于设置或清除 **IP_MULTICAST_TTL** socket 选项，该选项有助于指定允许一个数据包通过指定多播流量的 IP 跳数。

**语法:**

```
const socket.setMulticastTTL( ttl )
```

**参数:**该方法取整数值，表示允许数据包通过指定多播流量的 IP 跳数。

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the
// server.setMulticastTTL()  API

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client 
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");
let broadcast_address = 12345;

// Handling the message event
server.on("message", function (msg) {

   // Displaying the client message
   process.stdout.write("UDP String: "
                      + msg + "\n");

   // Exiting process
   process.exit();
})
.bind(broadcast_address, () => {
  // Enable the IP_MULTICAST_TTL socket option 
  // and specifiing the number of IP hopes
  // by using the setMulticastTTL() method
  server.setMulticastTTL(144);
});

// Client sending message to server
client.send("Hello", 0, 7,
    broadcast_address, "localhost");
```

**输出:**

```
UDP String: Hello
```

**示例 2:** **文件名:**

```
// Node.js program to demonstrate the
// server.setMulticastTTL()  API

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
  const address = server.address();
  console.log(`server listening 
    ${address.address}:${address.port}`);
});

// Binding server with port address
server.bind(1234, () => {

   // Enable the IP_MULTICAST_TTL socket option 
   // and specifiing the number of IP hopes
   // by using the setMulticastTTL() method
   server.setMulticastTTL(255);
});

// Client sending message to server
client.send("Hello", 0, 7, 
    1234, "localhost");
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
server listening 0.0.0.0:1234
UDP String: Hello
```

**参考资料:**[https://nodejs . org/dist/latest-v1 . x/docs/API/dgram . html # dgram _ socket _ setmulticast _ TTL](https://nodejs.org/dist/latest-v12.x/docs/api/dgram.html#dgram_socket_setmulticastttl_ttl)