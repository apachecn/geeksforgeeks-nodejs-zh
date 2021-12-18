# node . js write stream . getcolorddepth()方法

> 原文:[https://www . geesforgeks . org/node-js-write stream-getcolorthess-method/](https://www.geeksforgeeks.org/node-js-writestream-getcolordepth-method/)

**writeStream . GetColorDepth()**方法是 tty 模块内类 write stream 的内置应用编程接口，用于确定终端支持什么颜色。

**语法:**

```
const writeStream.getColorDepth([env])
```

**参数:**该方法接受包含环境变量的对象作为参数。

**返回值:**该方法返回该终端支持的颜色数。

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the
// writeStream.getColorDepth() method

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

  // Getting color depth
  // by using getColorDepth() API
  const col = WriteStream
      .getColorDepth(process.env);

  // Displaying the result
  process.stdout.write(msg + col);

  // Exiting process
  process.exit();
})
// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("No of color supported is :-  ",
         0, 28, 1234, "localhost");
```

**输出:**

```
No of color supported is :- 24
```

**示例 2:文件名:index.js**

```
// Node.js program to demonstrate the
// writeStream.getColorDepth() method

// Creating and initializing a
// WriteStream object
let WriteStream = process.stdout;

// Getting color depth
// by using getColorDepth() API
const col = WriteStream.getColorDepth(process.env);

// Displaying the result
console.log("No of color supported is :-  " + col);
```

使用以下命令运行 index.js 文件:

```
node index.js

```

**输出:**

```
No of color supported is :-  24

```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ write stream _ getcolorddepth _ env](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_writestream_getcolordepth_env)