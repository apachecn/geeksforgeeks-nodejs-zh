# node . js write stream . move cursor()方法

> 原文:[https://www . geesforgeks . org/node-js-write stream-move cursor-method/](https://www.geeksforgeeks.org/node-js-writestream-movecursor-method/)

**writeStream.moveCursor()** 方法是 tty 模块内类 writeStream 的内置应用编程接口，用于相对于其当前位置移动写流对象的光标。

**语法:**

```js
const writeStream.moveCursor(dx, dy[, callback])
```

**参数:**该方法取以下参数:

*   **DX:** The coordinate of the X axis relative to the current coordinate.
*   **dy:** Y-axis coordinate relative to the current coordinate.
*   **Callback: Callback function executed after** operation.

**返回值:**如果写流对象的光标相对于其当前位置移动，则该方法返回布尔值 true。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// writeStream.moveCursor() method

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

  // Moving cursor to with respect
  // to previous position by using
  // moveCursor() method
  const col = WriteStream.moveCursor(10, 7, ()=>{
  });

  // Displaying the result
  process.stdout.write(msg + col);

  // Exiting process
  process.exit();
})
// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("cursor is moved :-  ",
        0, 26, 1234, "localhost");
```

**输出:**

```js
cursor is moved :-  true
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// writeStream.moveCursor() method

// Creating and initializing a
// WriteStream object
let WriteStream = process.stdout;

// Moving cursor to with respect to
// previous position by using
// moveCursor() method
const col = WriteStream.moveCursor(10, 7, ()=>{
});

// Displaying the result
console.log("cursor is moved :-  " + col);
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
cursor is moved :-  true
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ write stream _ move cursor _ dx _ dy _ callback](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_writestream_movecursor_dx_dy_callback)