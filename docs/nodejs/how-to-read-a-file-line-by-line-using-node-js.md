# 如何使用 node.js 逐行读取文件？

> 原文:[https://www . geeksforgeeks . org/如何使用节点 js/逐行读取文件/](https://www.geeksforgeeks.org/how-to-read-a-file-line-by-line-using-node-js/)

逐行读取文件的能力允许我们读取大型文件，而无需将其完全存储到内存中。它有助于节省资源和提高应用程序的效率。它允许我们寻找所需的信息，一旦找到相关信息，我们就可以停止搜索过程，并可以防止不必要的内存使用。

我们将通过使用读线模块和读线模块来实现目标。

**方法 1:使用 Readline 模块:** Readline 是 Node.js 的一个原生模块，它是专门为从任何可读流中逐行读取内容而开发的。它可以用来从命令行读取数据。
因为模块是 Node.js 的原生模块，所以不需要任何安装，可以导入为

```js
const readline = require('readline');
```

由于 readline 模块只处理可读流，所以我们需要首先使用 fs 模块创建一个可读流。

```js
const file = readline.createInterface({
    input: fs.createReadStream('source_to_file'),
    output: process.stdout,
    terminal: false
});

```

现在，监听文件对象上的行事件。每当从流中读取新行时，都会触发事件:

```js
file.on('line', (line) => {
    console.log(line);
});

```

**示例:**

```js
// Importing the Required Modules
const fs = require('fs');
const readline = require('readline');

// Creating a readable stream from file
// readline module reads line by line 
// but from a readable stream only.
const file = readline.createInterface({
    input: fs.createReadStream('gfg.txt'),
    output: process.stdout,
    terminal: false
});

// Printing the content of file line by
//  line to console by listening on the
// line event which will triggered
// whenever a new line is read from
// the stream
file.on('line', (line) => {
    console.log(line);
});
```

**输出:**
![](img/2de878c1d6c25cff9f39861bb37a0c87.png)

**方法二:使用行阅读器模块:**行阅读器模块是 Node.js 中一行一行读取文件的开源模块，不是原生模块，需要使用 npm(Node Package Manager)使用命令安装:

```js
npm install line-reader --save
```

行阅读器模块提供了一种逐行读取文件的方法。它有一个回调函数，该函数有两个参数:行内容和一个布尔值，该值存储该行是否是文件的最后一行。

```js
const lineReader = require('line-reader');

lineReader.eachLine('source-to-file', (line, last) => {
    console.log(line);
});

```

**示例:**

```js
// Importing required libraries
const lineReader = require('line-reader');

// eachLine() method call on gfg.txt
// It got a callback function
// Printing content of file line by line
// on the console
lineReader.eachLine('gfg.txt', (line, last) => {
    console.log(line);
});
```

**输出:**
![](img/2de878c1d6c25cff9f39861bb37a0c87.png)