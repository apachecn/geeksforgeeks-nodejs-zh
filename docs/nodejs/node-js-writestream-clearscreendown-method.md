# node . js write stream . clearscreendown()方法

> 原文:[https://www . geesforgeks . org/node-js-write stream-clearscreendown-method/](https://www.geeksforgeeks.org/node-js-writestream-clearscreendown-method/)

**writeStream . clearscreendown()**方法是 tty 模块中类 write stream 的内置应用编程接口，用于从当前光标向下清除该写流对象。

**语法:**

```
writeStream.clearScreenDown([callback])
```

**参数:**这个方法不接受任何参数，但是它调用一个回调函数。

**返回值:**如果写对象为空，则该方法返回布尔值 true，否则返回 false。

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the
// writeStream.clearScreenDown() method

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

  // Clearing the write stream object
  // by using clearScreenDown() API
  const col = WriteStream.clearScreenDown();

  // Displaying the result
  process.stdout.write(msg + col);

  // Exiting process
  process.exit();
})
// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("The line is clear :-  ", 
        0, 26, 1234, "localhost");
```

**输出:**

```
The line is clear :-  true
```

**示例 2:** **文件名:**

```
// Node.js program to demonstrate the
// writeStream.clearScreenDown() method

// Creating and initializing a 
// WriteStream object
let WriteStream = process.stdout;

// Clearing the write stream object
// by using clearScreenDown() API
const col = WriteStream.clearScreenDown();

// Displaying the result
console.log("The write stream object"
    + " is clear :-  " + col);
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
The write stream object is clear :-  true

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ write stream _ clearscreendown _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_writestream_clearscreendown_callback)