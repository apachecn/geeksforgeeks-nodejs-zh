# Node.js filehandle.close()方法

> 原文:[https://www . geesforgeks . org/node-js-file handle-close-method/](https://www.geeksforgeeks.org/node-js-filehandle-close-method/)

**filehandle.close()** 方法用于异步*关闭给定的文件描述符*，从而清除与之关联的文件。这将允许文件描述符被其他文件重用。

在文件描述符上执行其他操作时，调用 filehandle.close()方法可能会导致未定义的行为。

**语法:**

```
filehandle.close();
```

**参数:**此方法不接受任何参数。

**示例:**该示例表示打开文件并关闭文件描述符。

**注意:**目录中应出现“input.txt”，文本如下:

```
Greetings from GeeksforGeeks
```

**文件名:app.js**

```
// Node.js program to demonstrate the   
// filehandle.close() Method

// Import the filesystem module  
const fs = require('fs');
const fsPromises = fs.promises;

async function readThenClose() {
    let filehandle = null;

    try {
        // Using the filehandle method 
        filehandle = await fsPromises
                .open('input.txt', 'r+');

        var data = await filehandle
                .readFile("utf8");

        console.log(data);

        filehandle.close();
        console.log("File Closed!");

    } catch (e) {
        console.log("Error", e);
    }
}

readThenClose().catch((error) => {
    console.log("Error", error)
});
```

使用以下命令运行 **app.js** 文件:

```
node app.js
```

**输出:**

```
Greetings from GeeksforGeeks
File Closed!
```

**参考:**T2】https://nodejs.org/api/fs.html#fs_filehandle_close