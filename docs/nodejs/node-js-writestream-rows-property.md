# Node.js writeStream.rows 属性

> 原文:[https://www . geesforgeks . org/node-js-write stream-rows-property/](https://www.geeksforgeeks.org/node-js-writestream-rows-property/)

**writeStream.rows** 属性是 tty 模块中类 writeStream 的内置应用程序编程接口，用于获取该写流对象的行数。

**语法:**

```
const writeStream.rows
```

**参数:**该属性不包含任何参数。

**返回值:**该属性返回写流对象的行数。

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the
// writeStream.rows property

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Handling the message event
server.on("message", function (msg) {

  // Creating and initializing a
  // WriteStream object
  let WriteStream = process.stdout;

  // Getting number of rows
  // by using rows API
  const col = WriteStream.rows;

  // Displaying the result
  process.stdout.write(msg + col);

  // Exiting process
  process.exit();
})
// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("Number of rows :- ",
        0, 21, 1234, "localhost");
```

**输出:**

```
Number of rows :- 10

```

**示例 2:** **文件名:**

```
// Node.js program to demonstrate the
// writeStream.rows property

// Creating and initializing a
// WriteStream object
let WriteStream = process.stdout;

// Getting number of rows
// by using rows API
const col = WriteStream.rows;

// Displaying the result
console.log("Number of rows :- " + col);
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
Number of rows :- 10

```

**参考**:[https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ write stream _ rows](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_writestream_rows)