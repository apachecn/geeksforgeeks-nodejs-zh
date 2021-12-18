# node . js 中 readFile 和 createReadStream 的区别

> 原文:[https://www . geesforgeks . org/node-js 中 readfile-and-createreadstream 之间的区别/](https://www.geeksforgeeks.org/difference-between-readfile-and-createreadstream-in-node-js/)

在本文中，我们将讨论 [Nodejs](https://www.geeksforgeeks.org/introduction-to-nodejs/) 中 readFile 和 createReadStream 的区别。这两个模块都允许我们打开文件/流并读取其中的数据。

**1。 [**readFile**](https://www.geeksforgeeks.org/node-js-fs-readfile-method/) :** fs 模块包含 readFile 方法。它用于通过将文件放入缓冲区来读取文件。这是一个异步方法，因此，它读取文件时不会阻止代码的执行。首先，我们将 fs 模块引入我们的应用程序，然后在其中使用 readFile 方法。

**语法:**

```
fs.readFile( filename, encoding, callback_function)
```

**参数:**

*   **文件名:**保存要读取的文件的路径。
*   **编码:**保存文件的编码。如果未指定选项，则返回原始缓冲区，默认值为“utf8”。
*   **callback_function:** 是读取文件后被调用的函数，包含两个参数 err 和 data。如果遇到任何错误，那么它会存储在 err 中，否则文件的内容会存储在数据中。

**返回值:**返回文件的内容。

**示例:**在本例中，我们使用 readFile 方法读取文件，要读取的文件是 output.txt。

**output.txt 文件:**

```
This is an output file read from readFile method.
```

## index.js

```
const fs = require('fs');
fs.readFile('output.txt', 'utf8', (err, data) => {
  console.log(`Data present in the file is::    ${data}`);
});
console.log('Outside readFile method');
```

**输出:**

```
Outside readFile method
Data present in the file is::   
This is an output file read from readFile method.
```

**2。[**createReadStream**](https://www.geeksforgeeks.org/node-js-fs-createreadstream-method/):**fs 模块包含内置的 API(应用编程接口)createReadStream。它允许我们打开一个文件/流并读取其中的数据。

**语法:**

```
fs.createReadStream(path, options)
```

**参数:**

*   **路径:**保存需要读取的文件路径。它可能是字符串，缓冲区的网址。
*   **选项:**为可选参数。我们可以传递一个字符串或对象给它。
*   **返回值:**返回 ReadObject 流的对象。

**示例:**在本例中，我们通过 createReadStream.on 方法读取文件名 output.txt。

**Output.txt 文件:**

```
This is an output file read from createReadStream method.
```

## index.js

```
const fs = require('fs');
const createReader = fs.createReadStream('output.txt');

createReader.on('data', (data) => {
  console.log(data.toString());
});

console.log('Outside createReader.on method');
```

**输出:**

```
Outside createReader.on method
This is an output file read from createReadStream method.
```

**readFile 与 createReadStream 的区别:**

<figure class="table">

| 

readFile

 | 

createReadStream

 |
| --- | --- |
| 它先将文件读入内存，然后将文件提供给用户。 | Read files in blocks according to the needs of users. |
| Reading the whole file is slow. | Because it has the attribute of bringing chunks, it is faster. |
| 它不会在请求太多的情况下扩展，因为它会尝试同时加载它们。 | 它是可伸缩的，因为它将内容直接管道传输到 HTTP响应对象 |
| 由于其属性，nodejs 在这种情况下更容易处理内存清理。 | In this case, it is not easy to clean up memory through nodejs. |

</figure>