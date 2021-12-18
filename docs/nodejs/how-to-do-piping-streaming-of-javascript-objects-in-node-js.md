# 如何在 Node.js 中进行 JavaScript 对象的管道化/流化？

> 原文:[https://www . geesforgeks . org/how-do-piping-streaming-of-JavaScript-objects-in-node-js/](https://www.geeksforgeeks.org/how-to-do-piping-streaming-of-javascript-objects-in-node-js/)

本文简要介绍了 node.js 中的管道/流实现，并解释了缓冲区、流等各个部分的工作以及如何在 node.js 中实现管道

**缓冲区:**这些是从一个地方传输到另一个地方的数据块的临时存储点，缓冲区充满了数据，然后继续传输。缓冲区一次传输一小块数据。缓冲区非常有用，因为我们不必等待完整的传输过程，因为我们填满了缓冲区，缓冲区是数据的临时存储点，然后可以一起传递。

**流:**它们是用于数据传输的数据处理方法。它提高了性能，因为甚至在数据完全传输之前就已经处理了数据。它将小块缓冲区收集在一起，当缓冲区填满时，它将数据向下传递到流中进行处理并发送到客户端。它们是一种数据处理方法，用于按照适当的顺序将输入读取或写入输出。缓冲区和流在一起播放在线视频时，您不需要等待完整的视频被处理，而是在缓冲区和流的帮助下一点一点地传输小片段。

**可读流:**可读流用于从任何来源提取信息，它们用于读取任何来源上存在的数据，然后我们可以使用这些数据传输到任何来源或存储在我们的系统中。可读流以*块*的形式发出事件(从缓冲区接收)，这是需要处理的一小部分数据。

**示例:**用一些示例文本在当前项目目录中创建一个 *read.txt* 文件，在本例中，我们有以下文本。

```
THIS IS READ.TXT FILE
```

**文件名:index . js**

## 【JavaScript】

```
// Requiring file system module
var fs = require('fs');

// Creating a read stream
var myReadStream = fs.createReadStream('read.txt', 'utf8');

myReadStream.on('data', function (chunk) {
  console.log("new chunk received");

  // Printing the chunk
  console.log(chunk);
});
```

**输出:**

```
new chunk received 
THIS IS READ.TXT FILE
```

**可写流:**可写流允许您将数据发送到任何指定的源，而不是任何文件或在线流。这些流还发出事件，以确保定期正常运行。

**示例:**使用以下代码创建一个 *index.js* 文件。

**文件名:index . js**

## 【JavaScript】

```
// Requiring file system module
var fs = require('fs');      

// Creating a write stream
// It will create a txt file in provided location
var myWriteStream =
    fs.createWriteStream(__dirname + '/write.txt');

// Writing on stream
myWriteStream.write("Greetings from GeeksforGeeks");
```

**输出:**将在当前目录中生成一个名为 *write.txt* 的新文件，该文件将包含以下数据。

```
Greetings from GeeksforGeeks
```

### **管道使用管道():**

管道是一种在缓冲区的帮助下直接将数据从一个流传输到另一个流的方法，这样数据传输过程可以在填满缓冲区后立即开始。换句话说，管道用于在不同的步骤中处理流数据。这是一种模块方法，用于在流之间传递转发错误，并在管道完成时正确清理和提供回调。

**示例:**在当前项目目录中创建一个带有一些示例文本的 *read.txt* 文件，在本例中，我们有以下文本。

```
THIS IS READ.TXT FILE
```

**文件名:index . js**

## 【JavaScript】

```
var fs = require('fs');
const zlib = require('zlib');
const { pipeline } = require('stream');

// Constructing promisify
const { promisify } = require('util');
const pipelineAsync = promisify(pipeline);

// Creating a read stream
var myReadStream = fs.createReadStream(
      __dirname + '/read.txt', 'utf8');

// Creating a write stream
var myWriteStream = fs.createWriteStream(
      __dirname + '/write.txt');

// Creating transform stream
const transform = zlib.createGzip();

(async function run() {
   try {

      // Pipelining three streams
      await pipelineAsync(

         // Reading from read stream
         myReadStream,

         // Transforming the file
         transform,

         // Writing on write stream
         myWriteStream
      );
      console.log("Pipeline accomplished");
   }
   catch (err) {
      console.error('pipeline failed with error:', err);
   }
})();
```

**输出:**我们会看到下面的输出和**write . txt*文件会在当前目录下生成。*

```
*Pipeline accomplished*
```

***注意:**应使用管道代替管道，因为管道不安全，但管道上的实施如下:*

***文件名:index . js***

## *【JavaScript】*

```
*// Requiring file system module
var fs = require('fs');      

// Creating a read stream
var myReadStream = fs.createReadStream(
        __dirname + '/read.txt','utf8');

// Creating a write stream
var myWriteStream = fs.createWriteStream(
        __dirname + '/write.txt');

// Piping using pipe
myReadStream.pipe(myWriteStream);  
console.log("Pipeing accomplished");*
```

***输出:**我们会看到下面的输出和**write . txt*文件会在当前目录下生成。**

```
**Pipeing accomplished**
```