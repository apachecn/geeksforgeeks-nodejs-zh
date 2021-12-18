# node . js write stream . getwindowsize()方法

> 原文:[https://www . geesforgeks . org/node-js-write stream-getwindowsize-method/](https://www.geeksforgeeks.org/node-js-writestream-getwindowsize-method/)

方法是 tty 模块中类 writeStream 的一个内置应用程序编程接口，用于获取这个 WriteStream 对象对应的 TTY 的大小。

**语法:**

```js
writeStream.getWindowSize()
```

**参数:**此方法不接受任何参数。

**返回值:**该方法返回包含 numColumns 和 numRows 的[numColumns，numRows]类型的数组。

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the
// writeStream..getWindowSize()  API

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

  // Getting window size of this write stream
  // object by using .getWindowSize() API
  const col = WriteStream.getWindowSize();

  // Displaying the result
  process.stdout.write(msg + col[0]);

  // Exiting process
  process.exit();
})// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("number columns of writestream :-  ", 0,
50, 1234, "localhost");
```

**输出:**

```js
number columns of writestream :-  182

```

**示例 2:** **文件名:**

```js
// Node.js program to demonstrate the
// writeStream..getWindowSize()  API

// Creating and initializing a WriteStream object
let WriteStream = process.stdout;

// Getting window size of this write stream
// object by using .getWindowSize() method
const col = WriteStream.getWindowSize();

// Displaying the result
console.log("number rows of writestream :-  " + col[1]);
```

使用以下命令运行 index.js 文件:

```js
node index.js

```

**输出:**

```js
number rows of writestream :-  14

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ write stream _ getwindowsize](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_writestream_getwindowsize)