# Node.js 流

> 原文:[https://www.geeksforgeeks.org/node-js-streams/](https://www.geeksforgeeks.org/node-js-streams/)

**流**是 Node.js 的基本概念之一。流是一种数据处理方法，用于将输入顺序地读取或写入输出。流用于以有效的方式处理读/写文件或交换信息。

官方 Node.js 文档将流定义为*“流是在 Node.js 中处理流数据的抽象接口”*流模块提供了实现流接口的 API。Node.js 中的流对象的例子可以是对 HTTP 服务器和进程的请求。stdout 都是流实例。简而言之，流是 Node.js 中的对象，它允许用户以连续的方式从源读取数据或将数据写入目标。

**访问流:**

```
const stream = require('stream');
```

**注意:**在处理大量数据时，streams 的强大之处在于，streams 实际上不是一次性将文件全部读入内存，而是读取数据块，处理其内容数据，而不是将其全部保存在内存中。

**Streams 相对于其他数据处理方法的优势:**

*   **时间效率:**我们不必等到整个文件传输完毕。我们一有数据就可以开始处理。
*   **内存高效:**在开始处理之前，我们不需要在内存中加载大量数据。

**node . js 中的流类型:**node . js 中有四种类型的流。

1.  **可写:**我们可以向这些流中写入数据。**示例:** fs.createWriteStream()。
2.  **可读:**我们可以从这些流中读取数据。**例:** fs.createReadStream()。
3.  **双工:**既可写又可读的流。**例:** net.socket。
4.  **转换:**可以在写入和读取数据时修改或转换数据的流。**示例:** zlib.createDeflate。

**一些使用流的节点应用编程接口有:**

*   净。插座()
*   process.stdin()
*   process.stdout()
*   process.stderr()
*   fs.createReadStream()
*   fs.createWriteStream()
*   net.connect()
*   http.request()
*   zlib.createGzip()函数
*   zlib.createGunzip()
*   zlib.createDeflate（）
*   zlib.createInflate()

**实现可读流:**我们将从 inStream 读取数据，并使用 process.stdout 将其回显到标准输出。

```
// Sample JavaScript Code for creating
// a Readable Stream
// Accessing streams
const { Readable } = require('stream');

// Reading the data 
const inStream = new Readable({
    read() { }
});

// Pushing the data to the stream
inStream.push('GeeksForGeeks : ');
inStream.push(
    'A Computer Science portal for Geeks');

// Indicates that no more data is
// left in the stream
inStream.push(null);

// Echoing data to the standard output
inStream.pipe(process.stdout);
```

**输出:**

```
GeeksForGeeks : A Computer Science portal for Geeks 
```

**实现一个可写流:**在 outStream 中，我们简单地将块记录为一个字符串。我们还调用回调函数来指示没有任何错误的成功。我们将从 inStream 中读取数据，并使用 process.stdout 将其回显到标准输出。

```
// Sample JavaScript Code for
// Writable Stream
// Accessing Streams
const { Writable } = require('stream');

// Whatever is passed in standard 
// input is out streamed here.
const outStream = new Writable({

    // The Write function takes three 
    // arguments
    // Chunk is for Buffer
    // Encoding is used in case we want
    // to configure the stream differently
    // In this sample code, Encoding is ignored 
    // callback is used to indicate 
    // successful execution
    write(chunk, encoding, callback) {
        console.log(chunk.toString());
        callback();
    }

});

// Echo the data to the standard output
process.stdin.pipe(outStream);
```

**输出:**

```
Hello Geeks
```