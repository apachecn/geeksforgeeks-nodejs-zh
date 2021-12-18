# Node.js 文件系统

> 原文:[https://www.geeksforgeeks.org/node-js-file-system/](https://www.geeksforgeeks.org/node-js-file-system/)

Node.js 是一个基于 Chrome 的 V8 JavaScript 引擎构建的 JavaScript 运行时。Node.js 帮助开发人员编写在服务器端运行的 JavaScript 代码，以生成动态内容并交付给 web 客户端。

使 Node.js 脱颖而出的两个特性是:

*   事件驱动
*   无阻塞输入输出模型

**关于 Node.js 文件系统:**处理文件的创建、读取、删除等操作。，Node.js 提供了一个名为 FS(文件系统)的内置模块。Node.js 通过提供标准 POSIX 函数的包装器来提供文件输入/输出的功能。根据用户要求，所有文件系统操作都可以有同步和异步形式。

要使用此文件系统模块，请使用 require()方法:

```
var fs = require('fs');
```

**文件系统模块常用:**

*   读取文件
*   写文件
*   追加文件
*   关闭文件
*   删除文件

**什么是同步和异步方法？**

*   **同步方法:**它们被称为**阻塞函数**，因为它等待每个操作完成，只有在此之后，它才执行下一个操作，因此阻塞下一个命令的执行，即一个命令直到&才被执行，除非查询已经完成执行以获得来自先前命令的所有结果。
*   **异步方法:**它们被称为**非阻塞函数**，因为它从不等待每个操作完成，而是自己先执行所有操作。一旦结果可用，将处理每个操作的结果，即每个命令将在前一个命令执行后立即执行。而前面的命令在后台运行，并在处理完数据后加载结果。
*   **用例:**
    *   如果您的操作不像从数据库中查询大量数据那样非常繁重，那么继续使用同步方式，否则使用异步方式。
    *   以异步的方式，你可以向用户显示一些进度指示器，而在后台你可以继续你的重量级工作。这是基于图形用户界面的应用程序的理想场景。
*   **Example of asynchronous and synchronous:** Create a text file named **input.txt** with the following content:

    ```
    GeeksforGeeks: A computer science portal
    ```

    现在让我们用下面的代码创建一个名为 **main.js** 的 js 文件:

    ```
    var fs = require("fs");

    // Asynchronous read
    fs.readFile('input.txt', function (err, data) {
       if (err) {
          return console.error(err);
       }
       console.log("Asynchronous read: " + data.toString());
    });
    ```

    **输出:**

    ```
    Asynchronous read: GeeksforGeeks: A computer science portal
    ```

    ```
    var fs = require("fs");

    // Synchronous read
    var data = fs.readFileSync('input.txt');
    console.log("Synchronous read: " + data.toString());
    ```

    **输出:**

    ```
    Synchronous read: GeeksforGeeks: A computer science portal
    ```

**打开文件:**fs . Open()方法用于创建、读取或写入文件。fs.readFile()方法仅用于读取文件，fs.writeFile()方法仅用于写入文件，而 fs.open()方法对文件执行多个操作。首先，我们需要加载 fs 类，这是一个访问物理文件系统的模块。

**语法:**

```
fs.open(path, flags, mode, callback)
```

**参数:**

*   **路径:**保存要读取的文件名，如果存储在其他位置，保存整个路径。
*   **标志:**标志表示要打开的文件的行为。所有可能的值都是(r，r+，rs，rs+，w，wx，w+，wx+，a，ax，a+，ax+)。
*   **模式:**设置文件模式，即 r 读、w 写、r+-读写。它默认设置为读写。
*   它是读取文件后调用的回调函数。它需要两个参数:

*   错误:如果出现任何错误。
*   数据:文件的内容。它在打开操作执行后被调用。

**示例:**让我们创建一个名为 **main.js** 的 js 文件，其代码如下打开一个文件 **input.txt** 进行读写。

```
var fs = require("fs");

// Asynchronous - Opening File
console.log("opening file!");
fs.open('input.txt', 'r+', function(err, fd) {
   if (err) {
      return console.error(err);
   }
   console.log("File open successfully");     
});
```

**输出:**

```
opening file!
File open successfully
```

**读取文件:**fs . read()方法用于读取 fd 指定的文件。此方法将整个文件读入缓冲区。

**语法:**

```
fs.read(fd, buffer, offset, length, position, callback)
```

**参数:**

*   **fd:** 这是 fs.open()方法返回的文件描述符。
*   **缓冲区:**这是数据将要写入的缓冲区。
*   **偏移量:**这是缓冲区中开始写入的偏移量。
*   **长度:**这是一个整数，指定要读取的字节数。
*   **位置:**这是一个整数，指定从文件中的哪个位置开始读取。如果位置为空，将从当前文件位置读取数据。
*   **回调:**是读取文件后调用的回调函数。它需要两个参数:
    *   **错误:**如果出现任何错误。
    *   **数据:**文件内容。

**示例:**让我们创建一个名为 **main.js** 的 js 文件，其代码如下:

```
var fs = require("fs");
var buf = new Buffer(1024);

console.log("opening an existing file");
fs.open('input.txt', 'r+', function(err, fd) {
   if (err) {
      return console.error(err);
   }
   console.log("File opened successfully!");
   console.log("reading the file");

   fs.read(fd, buf, 0, buf.length, 0, function(err, bytes){
      if (err){
         console.log(err);
      }
      console.log(bytes + " bytes read");

      // Print only read bytes to avoid junk.
      if(bytes > 0){
         console.log(buf.slice(0, bytes).toString());
      }
   });
});
```

**输出:**

```
opening an existing file
File opened successfully!
reading the file
GeeksforGeeks: A computer science portal
```

**写入文件:**如果文件已经存在，此方法将覆盖文件。fs.writeFile()方法用于将指定的数据异步写入文件。默认情况下，如果文件存在，它将被替换。“选项”参数可用于修改方法的功能。

**语法:**

```
fs.writeFile(path, data, options, callback)
```

**参数:**

*   **路径:**它是一个字符串、缓冲区、网址或文件描述整数，表示必须写入的文件路径。使用文件描述符将使其行为类似于 fs.write()方法。
*   **数据:**它是将被写入文件的字符串、缓冲区、类型数据或数据视图。
*   **选项:**它是一个字符串或对象，可用于指定将影响输出的可选参数。它有三个可选参数:
    *   **编码:**是指定文件编码的字符串值。默认值为“utf8”。
    *   **模式:**指定文件模式的整数值。默认值为 0o666。
    *   **标志:**它是一个字符串值，指定写入文件时使用的标志。默认值为“w”。
*   **回调:**是执行方法时会调用的函数。
    *   **错误:**如果操作失败，将会引发错误。

**示例:**让我们创建一个名为 **main.js** 的 js 文件，其代码如下:

```
var fs = require("fs");

console.log("writing into existing file");
fs.writeFile('input.txt', 'Geeks For Geeks', function(err) {
   if (err) {
      return console.error(err);
   }

   console.log("Data written successfully!");
   console.log("Let's read newly written data");

   fs.readFile('input.txt', function (err, data) {
      if (err) {
         return console.error(err);
      }
      console.log("Asynchronous read: " + data.toString());
   });
});
```

**输出:**

```
writing into existing file
Data written successfully!
Let's read newly written data
Asynchronous read: Geeks For Geeks
```

**追加到文件:**fs . appendfile()方法用于将数据同步追加到文件中。

**语法:**

```
fs.appendFile(filepath, data, options, callback);
```

或者

```
fs.appendFileSync(filepath, data, options);
```

**参数:**

*   **文件路径:**是指定文件路径的字符串。
*   **数据:**是强制的，它包含您追加到文件中的数据。
*   **选项:**是指定编码/模式/标志的可选参数。
*   **回调:**函数是必选项，在文件追加数据完成时调用。

**示例 1:** 让我们创建一个名为 **main.js** 的 js 文件，其代码如下:

```
var fs = require('fs');

var data = "\nLearn Node.js";

// Append data to file
fs.appendFile('input.txt', data, 'utf8',

    // Callback function
    function(err) { 
        if (err) throw err;

        //  If no error
        console.log("Data is appended to file successfully.")
});
```

**输出:**

```
Data is appended to file successfully.
```

**例 1:** 用于同步追加

```
var fs = require('fs');

var data = "\nLearn Node.js";

// Append data to file
fs.appendFileSync('input.txt', data, 'utf8');
console.log("Data is appended to file successfully.")
```

**输出:**

```
Data is appended to file successfully.
```

*   将数据追加到 input.txt 文件前:

    ```
    GeeksforGeeks: A computer science portal 
    ```

*   将数据追加到 input.txt 文件后:

    ```
    GeeksforGeeks: A computer science portal
    Learn Node.js
    ```

**关闭文件:**fs . close()方法用于异步关闭给定的文件描述符，从而清除与之关联的文件。这将允许文件描述符被其他文件重用。在文件描述符上执行其他操作时调用 fs.close()可能会导致未定义的行为。

**语法:**

```
fs.close(fd, callback)
```

**参数:**

*   **fd:** 表示要关闭的文件的文件描述符的整数。
*   **回调:**这是一个在执行方法时会被调用的函数。
    *   **err:** 这是一个如果方法失败会抛出的错误。

**示例:**让我们创建一个名为 **main.js** 的 js 文件，其代码如下:

```
// Close the opened file.
fs.close(fd, function(err) {
   if (err) {
      console.log(err);
   } 
   console.log("File closed successfully.");
}
```

**输出:**

```
File closed successfully.
```

**删除文件:**fs . unlink()方法用于从文件系统中删除文件或符号链接。此函数不适用于目录，因此建议使用 fs.rmdir()删除目录。

**语法:**

```
fs.unlink(path, callback)
```

**参数:**

*   **路径:**它是一个字符串、缓冲区或网址，代表必须删除的文件或符号链接。
*   **回调:**这是一个在执行方法时会被调用的函数。
    *   **err:** 这是一个如果方法失败会抛出的错误。

**示例:**让我们创建一个名为 **main.js** 的 js 文件，其代码如下:

```
var fs = require("fs");

console.log("deleting an existing file");
fs.unlink('input.txt', function(err) {
   if (err) {
      return console.error(err);
   }
   console.log("File deleted successfully!");
});
```

**输出:**

```
deleting an existing file
File deleted successfully!
```