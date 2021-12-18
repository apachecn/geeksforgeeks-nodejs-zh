# node . js Stream read . read()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-read-read-method/](https://www.geeksforgeeks.org/node-js-stream-readable-read-method/)

**read . read()方法**是 Stream 模块的内置应用编程接口，用于从内部缓冲区中读取数据。如果没有指定编码或者流在对象模式下工作，它将数据作为缓冲区对象返回。

**语法:**

```
readable.read( size )
```

**参数:**该方法接受单个参数**大小**，指定从内部缓冲区读取的字节数。

**返回值:**如果使用该方法，则在输出中显示该方法之后读取的数据，如果缓冲区中不存在数据，则返回空值。

下面的例子说明了在 Node.js 中**read . read()方法**的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// readable.read() method  

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method
  while (null !== (chunk = readable.read())) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});
console.log("done");
```

**输出:**

```
done
read: hello
```

这里，在上面的例子中，从缓冲区读取的数据是“hello”，所以它被返回。

**例 2:**

```
// Node.js program to demonstrate the     
// readable.read() method  

// Include fs module
const fs = require("fs");

// Constructing readable stream
const readable = fs.createReadStream("input.txt");

// Instructions for reading data
readable.on('readable', () => {
  let chunk;

  // Using while loop and calling
  // read method with parameter
  while (null !== (chunk = readable.read(1))) {

    // Displaying the chunk
    console.log(`read: ${chunk}`);
  }
});
console.log("done");
```

**输出:**

```
done
read: h
read: e
read: l
read: l
read: o

```

在上面的例子中，说明了数据的大小，因此在每个步骤中只从包含数据“hello”的文件“input.txt”中读取一个字节。

**参考:**[https://nodejs . org/API/stream . html # stream _ read _ read _ size](https://nodejs.org/api/stream.html#stream_readable_read_size)