# Node.js fs.open()方法

> 原文:[https://www.geeksforgeeks.org/node-js-fs-open-method/](https://www.geeksforgeeks.org/node-js-fs-open-method/)

**简介:**创建文件、写入文件或读取文件**使用 fs.open()方法**。 **fs.readFile()** 仅用于读取文件，同样 **fs.writeFile()** 仅用于写入文件，而 **fs.open()方法**对一个文件进行若干操作。首先我们需要加载 **fs** 类，它是访问物理文件系统的模块。为此**要求采用**方法。例如:`var fs = require('fs');`

**语法:**

```
fs.open( filename, flags, mode, callback )
```

**参数:**该方法接受如上所述和如下所述的四个参数:

*   **文件名:**保存要读取的文件的名称，如果存储在其他位置，则保存整个路径。
*   **标志:**必须打开文件的操作。
*   **模式:**设置文件模式，即 r 读、w 写、r+-读写。它默认设置为读写。
*   **回调:**是读取文件后调用的回调函数。它需要两个参数:
    *   **错误:**如果出现任何错误。
    *   **数据:**文件内容。执行打开操作后调用。

所有类型的**标志**描述如下:

| 旗 | 描述 |
| --- | --- |
| r | 打开文件进行读取，如果文件不存在，将引发异常。 |
| r+ | 打开文件进行读写。如果文件不存在，将引发异常。 |
| rs+ | 以同步模式打开文件进行读写。 |
| w | 打开文件进行写入。如果文件不存在，则创建该文件。 |
| women's extra large size 女式特大号 | 它与“w”相同，但如果路径存在，则失败。 |
| w+ | 打开文件进行读写。如果文件不存在，则创建该文件。 |
| wx+ | 它与' w+相同，但如果路径存在，则失败。 |
| a | 打开要追加的文件。如果文件不存在，则创建该文件。 |
| 削减 | 它与“a”相同，但如果路径存在，则失败。 |
| a+ | 打开文件进行读取和追加。如果文件不存在，则创建该文件。 |
| ax+ | 它与“a+”相同，但如果路径存在，则失败。 |

下面的例子说明了 Node.js 中的 fs.open()方法:

**例 1:**

```
// Node.js program to demonstrate the    
// fs.open() Method

// Include the fs module
var fs = require('fs');

// Open file demo.txt in read mode
fs.open('demo.txt', 'r', function (err, f) {
  console.log('Saved!');
});
```

**输出:**

```
Saved! 
```

**说明:**
文件打开，标志设置为读取模式。打开文件后，调用函数读取文件内容并存储在内存中。因为没有错误，所以打印“已保存”。

**例 2:**

```
// Node.js program to demonstrate the    
// fs.open() Method

// Include the fs module
var fs = require('fs');

console.log("Open file!");

// To open file in write and read mode,
// create file if doesn't exists.
fs.open('demo.txt', 'w+', function (err, f) {
   if (err) {
      return console.error(err);
   }
   console.log(f);
   console.log("File opened!!");     
});
```

**输出:**

```
Open file!
10
File Opened!
```

**说明:**以读写方式打开文件‘demo . txt’，然后调用函数。当我们打印“f”值时，输出显示文件中的一个数字。

**参考:**T2【https://nodejs . org/API/fs . html # fs _ fs _ open _ path _ flags _ mode _ callback