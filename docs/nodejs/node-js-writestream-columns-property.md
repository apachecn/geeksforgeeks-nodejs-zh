# Node.js writeStream.columns 属性

> 原文:[https://www . geesforgeks . org/node-js-write stream-columns-property/](https://www.geeksforgeeks.org/node-js-writestream-columns-property/)

**writeStream.columns** 属性是 tty 模块中类 writeStream 的内置应用程序编程接口，用于获取该写流对象的列数。

**语法:**

```
const writeStream.columns
```

**返回值:**该属性返回写流对象包含的列数。

**示例 1:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// writeStream.columns property

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

    // Getting number of columns
    // by using columns API
    const col = WriteStream.columns;

    // Displaying the result
    process.stdout.write(msg + col);

    // Exiting process
    process.exit();
})

    // Binding server with port
    .bind(1234, () => {
    });

// Client sending message to server
client.send("Number of Columns :- ",
        0, 21, 1234, "localhost");
```