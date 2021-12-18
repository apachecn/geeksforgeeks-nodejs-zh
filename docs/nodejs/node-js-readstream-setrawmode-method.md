# node . js readstream . setrawmode()方法

> 原文:[https://www . geesforgeks . org/node-js-readstream-set raw mode-method/](https://www.geeksforgeeks.org/node-js-readstream-setrawmode-method/)

**readStream.setRawMode()** 方法是“tty”模块内类 readStream 的内置应用编程接口，用于将 ReadStream 对象的原始模式设置为作为原始设备工作。

**语法:**

```
const readStream.setRawMode( mode )
```

**参数:**该方法以布尔值为自变量。

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// readStream.setRawMode() method

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

    // Setting the read stream Raw mode
    // by using setRawMode() method
    ReadStream.setRawMode(false);

    // Checking if it is configured or not
    // by using isRaw() method
    const status = ReadStream.isRaw;

    // Displaying the result
    if (status)
        process.stdout.write(msg + "configured" + "\n");
    else
        process.stdout.write(msg + "not configured" + "\n");

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

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// readStream.setRawMode() method

// Creating and initializing a ReadStream object
let ReadStream = process.stdin;

// Setting the read stream Raw mode
// by using setRawMode() method
ReadStream.setRawMode(true);

// Checking if it is configured or not
// by using isRaw() method
const status = ReadStream.isRaw;

// Displaying the result
if(status)
    console.log("It is configured");
else
    console.log("It is not configured");
```

**输出:**

```
It is configured
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v1 . x/docs/API/tty . html # tty _ readstream _ setrawmode _ mode](https://nodejs.org/dist/latest-v12.x/docs/api/tty.html#tty_readstream_setrawmode_mode)