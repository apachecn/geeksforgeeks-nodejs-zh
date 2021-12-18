# Node.js Readline()模块

> 原文:[https://www.geeksforgeeks.org/node-js-readline-module/](https://www.geeksforgeeks.org/node-js-readline-module/)

Node.js 中的 **Readline 模块**允许逐行读取输入流。该模块包装过程标准输出和过程标准输入对象。Readline 模块使输入和读取用户给出的输出变得更加容易。要使用该模块，请创建一个新的 JavaScript 文件，并在应用程序启动时编写以下代码–

```js
var readline = require('readline');
```

Readline 模块提供了与用户交互的不同方法。
**与用户的交互:**对于交互，我们将首先为输入和输出创建一个界面。要创建接口，请编写以下代码–

## java 描述语言

```js
var readline = require('readline');

var rl = readline.createInterface(
     process.stdin, process.stdout);
```

这里， **createInterface()** 方法采用两个参数。第一个参数用于标准输入，第二个参数用于读取标准输出。

## java 描述语言

```js
rl.question('What is your age? ', (age) => {
    console.log('Your age is: ' + age);
});
```