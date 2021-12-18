# node . js write stream . hascolors()方法

> 原文:[https://www . geesforgeks . org/node-js-write stream-hascolors-method/](https://www.geeksforgeeks.org/node-js-writestream-hascolors-method/)

**writeStream.hasColors()** 方法是 tty 模块中类 writeStream 的内置应用程序编程接口，用于检查该写流对象是否至少支持 count 中提供的颜色。

**语法:**

```
const writeStream.hasColors([count][, env])
```

**参数:**此方法接受以下参数:

*   **Count:** is the number of different types of colors.
*   **env:** The object containing the environment variable to be checked.

**返回值:**当且仅当 writeStream 支持的颜色至少与 count 中提供的一样多时，此方法返回布尔值 true。

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the
// writeStream.hasColors() property

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Handling the message event
server.on("message", function (msg) {

  // Creating and initializing a WriteStream object
  let WriteStream = process.stdout;

  // Checking if the this object has the exactly
  // same color or not requested by count
  // by using hasColors() API
  const col = WriteStream.hasColors(16, 777, 216);

  // Displaying the result
  process.stdout.write(msg + col);

  // Exiting process
  process.exit();
})
// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("This object supports at least as"
      + " many colors as provided in count: ",
        0, 98, 1234, "localhost");
```

**输出:**

> 该对象支持的颜色至少和 count 中提供的一样多:true

**示例 2:** **文件名:index.js**

## Javascript

```
// Node.js program to demonstrate the
// writeStream.hasColors() method

// Creating and initializing a WriteStream object
let WriteStream = process.stdout;

// Checking if the this object has the exactly
// same color or not requested by count
// by using hasColors() method
const col = WriteStream.hasColors(256);

// Displaying the result
console.log("This object supports at least as "
  + "many colors as provided in count: ", col);
```

使用以下命令运行 index . js 文件:

```
node index.js

```

**输出:**

> 该对象至少支持 count 中提供的颜色数量:true

**参考:** [https://nodejs](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_writestream_hascolors_count_env)