# node . js write stream . clearline()方法

> 原文:[https://www . geesforgeks . org/node-js-write stream-clearline-method/](https://www.geeksforgeeks.org/node-js-writestream-clearline-method/)

**writeStream.clearLine()** 是模块内类 writeStream 的内置应用编程接口，用于清除该写流对象的当前行。

**语法:**

```js
writeStream.clearLine(dir[, callback])
```

**参数:**该方法将以下参数作为参数:

*   **dir:** An integer value that defines line selection.
*   **Callback:** Called after the operation is completed.

**返回值:**如果写对象行为空，则该方法返回布尔值 true，否则返回 false。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// writeStream.clearLine() method

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

  // Clearing the line
  // by using clearLine() API
  const col = WriteStream.clearLine();

  // Displaying the result
  process.stdout.write(msg + col);

  // Exiting process
  process.exit();
})// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("The line is clear :-  ",
    0, 26, 1234, "localhost");
```

**输出:**

```js
The line is clear :-  true
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// writeStream.clearLine() method

// Creating and initializing a
// WriteStream object
let WriteStream = process.stdout;

// Clearing the line
// by using clearLine() API
const col = WriteStream.clearLine();

// Displaying the result
console.log("The line is clear :-  " + col);
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
The line is clear :-  true
```

**参考:**T2】https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ write stream _ clearline _ dir _ callback