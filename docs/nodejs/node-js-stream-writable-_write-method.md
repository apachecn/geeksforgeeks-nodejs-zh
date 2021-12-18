# Node.js 流可写。_write()方法

> 原文:[https://www . geesforgeks . org/node-js-stream-write-_ write-method/](https://www.geeksforgeeks.org/node-js-stream-writable-_write-method/)

**可写。_write()方法**是 Stream 模块的内置应用编程接口，用于实现可写流。可写的。_write()方法在定义它的类中加上了下划线。此外，用户程序不能直接调用它。此方法通过使用子类实现，并且仅由内部可写类方法调用。

**语法:**

```
writable._write( chunk, encoding, callback )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **区块:**是要写入的数据，可以是缓冲区、字符串或任何类型。
*   **编码:**如果区块是字符串类型，则使用的编码类型。
*   **回调:**是检查写操作完成还是失败而调用的方法。如果调用没有成功，传递给回调的第一个参数必须是“Error”对象，如果写入成功，则为 null。

下面的例子说明了**可写的用法。_write()方法** Node.js:

**例 1:**

```
// Node.js program to demonstrate the     
// writable._write() method

// Constructing writable stream
const {Writable} = require("stream");

// Function to check char
const charchecks = new Writable({

  // Implementing write function
  write(chunk, encoding, callback){

    // Defining string
    const string = chunk.toString();

    // If string contains below character
    // then an error is show else the
    // written string is returned
    if(string.includes("\/")){
      callback(Error("Forbidden character"));

    }
    else
    {
      // Displays string
      console.log(string);
      callback();
    }
  }
});

// Piping standard input to standard output, if
// you don't enter the forbidden character else
// it throws error
process.stdin.pipe(charchecks).on('error', console.log);

// Enter the string to be written
console.log("Enter the string: ");
```

现在，您需要运行代码并在运行时输入字符串来获得输出。

```
Enter the string:
GeeksforGeeks
GeeksforGeeks // Output

Enter the string:
GfG
GfG // Output

Enter the string:
Nidhi
Nidhi //Output

```

现在，要退出它，你需要按下 control + C。

**例 2:**

```
// Node.js program to demonstrate the     
// writable._write() method

// Constructing writable stream
const {Writable} = require("stream");

// Function to check char
const charchecks = new Writable({

  // Implementing write function
  write(chunk, encoding, callback){

    // Defining string and encoding it
    const string = chunk.toString('hex');

    // Prints encoded string
    console.log(string);

    // If the encoded string contains below 
    // character then an error is shown else
    // the length of the encoded string is 
    // returned
    if(string.includes("c")){

      callback(Error("This is an error."));

    }
    else
    {
      // Displays length of the encoded string
      console.log(string.length);
      callback();
    }
  }
});

// Piping standard input to standard output, if
// you don't enter the forbidden character else
// it throws an error
process.stdin.pipe(charchecks).on('error', console.log);

// Enter the string to be written
console.log("Enter the string: ");
```

现在，您需要运行代码并在运行时输入字符串来获得输出。
**输出:**

```
Enter the string:
Geeks
4765656b730a   // encoded string
12             // length of encoded string
Nidhi
4e696468690a
12
portal
706f7274616c0a   // encoded string contains "c" so length of it  
                 // is not returned and an error is thrown
Error: This is an error.
    at Writable.write [as _write] (/home/runner/QuickwittedDistantCensorware/index.js:25:16)
    at doWrite (_stream_writable.js:415:12)
    at writeOrBuffer (_stream_writable.js:399:5)
    at Writable.write (_stream_writable.js:299:11)
    at ReadStream.ondata (_stream_readable.js:710:20)
    at ReadStream.emit (events.js:198:13)
    at ReadStream.EventEmitter.emit (domain.js:448:20)
    at addChunk (_stream_readable.js:288:12)
    at readableAddChunk (_stream_readable.js:269:11)
    at ReadStream.Readable.push (_stream_readable.js:224:10)

```

现在，要退出它，你需要按 control C.
所以，这里抛出一个错误，因为运行时输入包括所述的禁止字符，所以，抛出一个错误。

**参考:**[https://nodejs . org/API/stream . html # stream _ write _ write _ chunk _ encoding _ callback _ 1](https://nodejs.org/api/stream.html#stream_writable_write_chunk_encoding_callback_1)