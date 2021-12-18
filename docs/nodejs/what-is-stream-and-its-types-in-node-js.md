# node . js 中什么是流及其类型？

> 原文:[https://www . geesforgeks . org/什么是流及其在节点中的类型-js/](https://www.geeksforgeeks.org/what-is-stream-and-its-types-in-node-js/)

流是一种数据处理方式，它通过读取或写入输入(文件、网络通信和任何类型的端到端信息交换)来帮助我们获得顺序输出。也就是说，它们允许您从源中读取数据或将其写入目标，或者以不间断和持续的方式执行任何其他特定任务。对于 Node.js 来说，流并不是一个独特的概念，在相当长的时间里，它都是 Unix 的一部分。管道操作符用于通过传递流使程序相互反应。因此，Node.js 流被用作所有流 API 的基础。

**举例:**当你在流媒体 YouTube、网飞、Spotify 的时候，它不是一次下载全部内容，而是在你不停浏览的同时，小块下载。另一个例子可以是在脸书或 WhatsApp 上聊天，数据在两个人之间持续流动。
这是因为数据流不是一次读取内存中的所有数据，而是将其处理成更小的片段，使大文件更容易读取。这很有用，因为有些文件大于设备上的可用空间。因此，该流使这些文件可读。

**流的优势:**

1.  **内存效率:** Stream 具有内存(空间)效率，因为它们使您能够在处理文件之前以更小的块而不是整个块下载文件，从而节省空间。
2.  **时间效率:** Stream 是时间高效的，因为您开始以更小的块处理数据，所以与一般方式相比，该过程开始得更早，在一般方式下，您必须下载整个数据才能处理它。因此，这种早期处理节省了大量时间。
3.  **可组合数据:**数据的组合是因为流的管道能力，这使它们连接在一起，尽管代码很重。这意味着从一个输入到另一个输出的过程还在继续。

**溪流类型:**

1.  **可读流:**它是您可以有序接收和读取数据的流。但是，你不允许发送任何东西。例如，fs.createReadStream()允许我们读取文件的内容。
2.  **可写流:**可以有序发送数据，但不允许接收回来的流。例如，fs.createWriteStream()允许我们将数据写入文件。
3.  **双联流:**是既可读又可写的流。因此，您可以一起发送和接收数据。比如网。套接字是一个 TCP 套接字。
4.  **转换流:**它是用于在读取数据时修改或转换数据的流。转换流本质上基本上是双工的。例如，zlib.createGzip 流用于使用 Gzip 压缩数据。

**一个流中不同的操作有:**

1.  **Reading from a stream:** Create a file named **input.txt** with the following text:
    *This is a code to learn about the reading from a stream.*

    **文件名:main.js**

    ```
    var fs = require("fs"); 
    var data = ''; 

    // Create a readable stream 
    var readerStream = fs.createReadStream("input.txt"); 
    // Set the encoding to be utf8. 
    readerStream.setEncoding("UTF8"); 

    // Handling data stream event
    readerStream.on("data", function(chunk) { 
        data += chunk; 
    }); 

    // Handling end stream event
    readerStream.on("end",function() { 
        console.log(data); 
    }); 

    // Handling error stream event
    readerStream.on("error", function(err) { 
        console.log(err.stack); 
    }); 
    ```

    使用以下命令运行 **main.js** 文件:

    ```
    $ node main.js
    ```

    上述命令的输出如下所示:

    ```
    This is a code to learn about the reading from a stream.
    ```

2.  **Writing to a stream**

    **文件名:main.js**

    ```

    var fs = require('fs');
    var data = 'This is a code to learn"
        + " about writing in a stream.';

    // Create a writable stream 
    var writerStream = 
        fs.createWriteStream('output.txt');

    // Write the data to stream with
    // encoding to be utf8 
    writerStream.write(data, 'UTF8');

    // Mark the end of file 
    writerStream.end();

    // Handling finish stream event
    writerStream.on('finish', function () {
    });

    // Handling error stream event
    writerStream.on('error', function (err) {
        console.log(err.stack);
    });  
    ```

    使用以下命令运行 **main.js** 文件:

    ```
    $ node main.js
    ```

    执行上述命令后，将在当前目录中创建一个名为 **output.txt** 的文件，其文本如下:

    ```
    This is a code to learn about writing in a stream.
    ```

3.  **Piping the stream:** Piping is an operation or a mechanism where we provide the output of one stream (readable, i.e., the source file) of data as the input to another stream (write-able, i.e. the destination file). It is normally used to get data from one stream (i.e. read from source) and pass the output of that stream to another stream (i.e. write to destination) without managing the flow yourself. It is the easiest way to consume streams. There is no limit on piping operations. It is used to process streamed data in multiple ways. For example, reading from one file and writing it to another.

    用以下文本创建一个名为 **input.txt** 的文件:

    ```
    This is a code to learn about piping the stream.
    ```

    **文件名:main.js**

    ```
    var fs = require('fs'); 

    // Create a readable stream 
    var readerStream = fs.createReadStream('input.txt'); 

    // Create a writable stream 
    var writerStream = fs.createWriteStream('output.txt'); 

    // Pipe the read and write operations 
    // read input.txt and write data to output.txt 
    readerStream.pipe(writerStream); 
    ```

    使用以下命令运行 **main.js** 文件:

    ```
    $ node main.js
    ```

    执行上述命令后，将在当前目录下创建一个名为 **output.txt** 的文件，其文本如下:

    ```
    This is a code to learn about piping the stream.
    ```

4.  **Chaining the stream:** Chaining of the stream is a mechanism of creating a chain of multiple stream operations by connecting the output of one stream with another stream. It is normally used with piping operations. For example, we will use piping and chaining to first compress a file and then decompress the same.

    **文件名:main.js**

    ```
    var fs = require('fs'); 
    var zlib = require('zlib'); 

    // Compress the file input.txt to input.txt.gz 
    fs.createReadStream('input.txt') 
    .pipe(zlib.createGzip()) 
    .pipe(fs.createWriteStream('input.txt.gz')); 

    console.log('File Compressed.'); 
    ```

    使用以下命令运行 **main.js** 文件:

    ```
    $ node main.js
    ```

    上述命令的输出如下所示:

    ```
    File Compressed.
    ```

    你会发现 **input.txt** 已经被压缩了，它在当前目录中创建了一个文件**input.txt.gz**。

    现在解压上面创建的文件的代码如下所示:
    **文件名:main.js**

    ```
    var fs = require('fs'); 
    var zlib = require('zlib'); 

    // Decompress the file input.txt.gz to input.txt 
    fs.createReadStream('input.txt.gz') 
    .pipe(zlib.createGunzip()) 
    .pipe(fs.createWriteStream('input.txt')); 

    console.log('File Decompressed.'); 
    ```

    使用以下命令运行 **main.js** 文件:

    ```
    $ node main.js
    ```

    上述命令的输出如下所示:

    ```
    File Decompressed.
    ```

    你会发现**input.txt.gz**已经解压了。