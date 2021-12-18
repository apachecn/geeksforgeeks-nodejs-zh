# node . js 中的阻塞和非阻塞

> 原文:[https://www . geesforgeks . org/blocking-and-non-blocking-in-node-js/](https://www.geeksforgeeks.org/blocking-and-non-blocking-in-node-js/)

Node.js 基于事件驱动的非阻塞 I/O 模型。本文讨论了 Node.js 中的阻塞和非阻塞是什么意思。

**阻塞:**是指在当前操作完成之前，阻止进一步操作。阻塞方法同步执行。同步意味着程序逐行执行。程序等待，直到被调用的函数或操作返回。

**示例:**以下示例使用 [readFileSync()](https://www.geeksforgeeks.org/node-js-fs-readfilesync-method/) 函数读取文件并演示 node . js

## index . js

```js
const fs = require('fs');

const filepath = 'text.txt';

// Reads a file in a synchronous and blocking way 
const data = fs.readFileSync(filepath, {encoding: 'utf8'});

// Prints the content of file
console.log(data);

// This section calculates the sum of numbers from 1 to 10
let sum = 0;
for(let i=1; i<=10; i++){
    sum = sum + i;
}

// Prints the sum
console.log('Sum: ', sum);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
This is from text file.
Sum:  55
```

**非阻塞:**指不阻塞进一步操作执行的程序。非阻塞方法异步执行。异步意味着程序不一定逐行执行。程序调用该函数并进入下一个操作，而不等待它返回。

**示例:**以下示例使用 [readFile()](https://www.geeksforgeeks.org/node-js-fs-readfile-method/) 函数读取文件并演示 node . js

## index . js

```js
const fs = require('fs');

const filepath = 'text.txt';

// Reads a file in a asynchronous and non-blocking way 
fs.readFile(filepath, {encoding: 'utf8'}, (err, data) => {
    // Prints the content of file
    console.log(data);
});

// This section calculates the sum of numbers from 1 to 10
let sum = 0;
for(let i=1; i<=10; i++){
    sum = sum + i;
}

// Prints the sum
console.log('Sum: ', sum);
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Sum:  55
This is from text file.
```

**注意:**在非阻塞程序中，总和实际上打印在文件内容之前。这是因为程序不会等待 readFile()函数返回并移动到下一个操作。当 readFile()函数返回时，它会打印内容。