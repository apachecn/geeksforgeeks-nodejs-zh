# node . js 中 API 函数的类型

> 原文:[https://www . geesforgeks . org/type-of-API-functions-in-node-js/](https://www.geeksforgeeks.org/types-of-api-functions-in-node-js/)

[<u>API</u>](https://www.geeksforgeeks.org/introduction-to-apis/) 代表应用编程接口。它由各种通信协议和子程序组成，程序可以使用它们进行内部通信。有各种类型的应用程序接口，如网络接口、本地接口、程序接口等。它们是最有效、最可靠的输出方式之一。

**API 函数在**[**<u>node . js</u>**](https://www.geeksforgeeks.org/introduction-to-nodejs/)**<u>中的类型:</u>**

1.  Asynchronous, nonblocking function
2.  Synchronization, blocking function

**异步、非阻塞函数:**顾名思义，这些函数异步运行。这意味着当 Node.js 向 API 发出数据请求时，在收到数据之前不会被阻塞。相反，它将在调用后继续移动到下一个应用编程接口，来自 Node.js 事件的通知机制将响应服务器对上一个应用编程接口的调用。通俗地说，这些函数允许在处理请求时进一步工作。示例:电子邮件、在线论坛

**同步、阻塞功能:**与异步功能相反，同步功能充当阻塞功能。这意味着这些函数将使调用系统等待响应。因此，当系统使用同步 API 时，它期望在发出请求时获得即时数据。这些类型的应用编程接口用于高可用性和连接性以及低延迟的情况。通俗地说，应用程序将请求并等待响应，直到返回值。示例:即时消息、视频会议

**示例:**假设我们有一个名为 **data.json** 的 JSON 文件，其中包含如下某些数据:

```js
{
    "name": "John",
    "age": 50,
    "gender": "male"
}
```

现在，我们将使用异步和同步函数来读取这些数据。Node.js 内置了一个名为 [<u>fs</u>](https://nodejs.org/api/fs.html#fs_file_system) 的模块，代表文件系统，可以用来以建模的方式与文件进行交互。要使用它，我们需要如下要求:

```js
const fs = require('fs');
```

我们在应用中使用了以下两个函数:

*   In order to read files asynchronously, we use the [<u>Readfile ()</u>](https://nodejs.org/api/fs.html#fs_fs_readfile_path_options_callback) method, which is supported by the **FS** module.
*   In order to read files synchronously, we used the [<u>ReadFile Sync ()</u>](https://nodejs.org/api/fs.html#fs_fs_readfilesync_path_options) method supported by **FS** module.

**例:**

## js

```js
// Requiring inbuilt module
const fs = require('fs');

// Asynchronous function
fs.readFile('data.json', 'utf8', function (err,data) {
  if (err) {
    return console.log(err);
  }
  console.log("Below is the Data from Asynchronous function call")
  console.log(data);
});

// Synchronous function
var data = fs.readFileSync('data.json','utf8');
console.log("Below is the Data from Synchronous function call")
console.log(data);
```

**运行应用程序的步骤。**

使用以下命令运行 **index.js** 文件。

```js
node index.js
```

**输出:**我们将在您的终端屏幕上看到以下输出:

```js
Below is the Data from Synchronous function call
{
    "name": "John",
    "age": 50,
    "gender": "male"
}
Below is the Data from Asynchronous function call
{
    "name": "John",
    "age": 50,
    "gender": "male"
}
```

当执行上述代码时，它将产生与异步相同的输出，并且在**相同的**时间范围内。这背后的原因是，当我们读取一两个文件时，这两种方法之间的差异不会很大。但是，当我们使用一个数据库操作并处理多个请求时，区别将非常明显，因为它将直接影响性能。