# Node.js writeStream.cursorTo()方法

> 原文:[https://www . geesforgeks . org/node-js-write stream-cursorto-method/](https://www.geeksforgeeks.org/node-js-writestream-cursorto-method/)

**writeStream.cursorTo()** 方法是 tty 模块内类 writeStream 的内置应用编程接口，用于将写流对象的光标移动到指定位置。

**语法:**

```
writeStream.cursorTo(x[, y][, callback])
```

**参数:**该方法取以下参数:

*   **X:** It stores the X-axis coordinates of the cursor position.
*   **Y:** It stores the Y-axis coordinates of the cursor position.
*   **Callback: Callback function executed after** operation.

**返回值:**如果写流对象的光标移动到指定位置，该方法返回布尔值 true。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// writeStream.cursorTo() method

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

  // Moving cursor to a specified position
  // by using cursorTo() API
  const col = WriteStream.cursorTo(10, 7, ()=>{ 
  });

  // Displaying the result
  process.stdout.write(msg + col);

  // Exiting process
  process.exit();
})
// Binding server with port
.bind(1234, () => {
});

// client sending message to server
client.send("cursor is moved :-  ",
        0, 26, 1234, "localhost");
```

**输出:**

```
cursor is moved :-  true
```

**示例 2:** **文件名:index . js**

## Javascript

```
// Node.js program to demonstrate the
// writeStream.cursorTo() method

// Creating and initializing a
// WriteStream object
let WriteStream = process.stdout;

// Moving cursor to a specified position
// by using cursorTo() API
const col = WriteStream.cursorTo(10, 7, ()=>{ 
});

// Displaying the result
console.log("cursor is moved :-  " + col);
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
cursor is moved :-  true
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ write stream _ cursorto _ x _ y _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_writestream_cursorto_x_y_callback)