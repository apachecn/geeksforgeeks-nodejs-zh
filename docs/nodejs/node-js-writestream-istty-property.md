# Node.js writeStream.isTTY 属性

> 原文:[https://www . geesforgeks . org/node-js-write stream-istty-property/](https://www.geeksforgeeks.org/node-js-writestream-istty-property/)

**writeStream.isTTY** 属性是“TTY”模块中类 writeStream 的内置应用程序编程接口，用于检查写流对象是否是 tty 的实例。对于 tty、writeStream，它将始终返回 true。

**语法:**

```js
const writeStream.isTTY
```

**返回值:**如果写流对象是 tty 的实例，则该属性返回 true。

**示例 1:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// writeStream.isTTY property

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Catching the message event
server.on("message", function (msg) {

    // Creating and initializing a
    // WriteStream object
    let WriteStream = process.stdout;

    // Checking if it is instance of TTY
    // or not by using isTTY() method
    const status = WriteStream.isTTY;

    // Displaying the result
    if (status)
        process.stdout.write(msg
            + "an instant of TTY" + "\n");
    else
        process.stdout.write(msg
            + "not an instant of TTY" + "\n");

    // Exiting process
    process.exit();
})

// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("It is ", 0, 7, 1234, "localhost");
```