# Node.js readStream.isRaw 属性

> 原文:[https://www . geesforgeks . org/node-js-readstream-israw-property/](https://www.geeksforgeeks.org/node-js-readstream-israw-property/)

**readStream.isRaw** 属性是 tty 模块中类 **ReadStream** 的内置应用程序编程接口，用于检查读取流对象当前是否配置为作为原始设备运行。

**语法:**

```
const status = ReadStream.isRaw;
```

**返回值:**当且仅当读取流对象当前被配置为作为原始设备运行时，该属性返回 true。

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the
// readStream.isRaw property

// Importing dgram module
var dgram = require('dgram');

// Creating and initializing client
// and server socket
var client = dgram.createSocket("udp4");
var server = dgram.createSocket("udp4");

// Catching the message event
server.on("message", function (msg) {

    // Creating and initializing a
    // ReadStream object
    let ReadStream = process.stdin;

    // Checking if it is configured or
    // not by using isRaw() method
    const status = ReadStream.isRaw;

    // Displaying the result
    if (status) {
        process.stdout.write(msg 
            + "configured" + "\n");
    } else {
        process.stdout.write(msg 
            + "not configured" + "\n");
    }

    // Exiting process
    process.exit();
})

// Binding server with port
.bind(1234, () => {
});

// Client sending message to server
client.send("It is ", 0, 7, 1234, "localhost");
```

**输出:**

```
It is not configured
```

**示例 2:** **文件名:**

```
// Node.js program to demonstrate the
// readStream.isRaw property

// Creating and initializing a 
// ReadStream object
let ReadStream = process.stdin;

// Setting the read stream Raw mode
// by using setRawMode() method
ReadStream.setRawMode(true);

// Checking if it is configured or not 
// by using isRaw() method
const status = ReadStream.isRaw;

// Displaying the result
if(status) {
   console.log("It is configured");
} else {
   console.log("it is not configured");
}
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**

```
It is configured
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/tty . html # tty _ readstream _ israw](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_readstream_israw)