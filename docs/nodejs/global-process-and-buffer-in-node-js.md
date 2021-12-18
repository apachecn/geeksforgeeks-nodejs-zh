# node . js 中的全局、进程和缓冲区

> 原文:[https://www . geesforgeks . org/global-process-and-buffer-in-node-js/](https://www.geeksforgeeks.org/global-process-and-buffer-in-node-js/)

**全局:**node . js 中的全局对象在所有模块中都是可用的，并且在本地作用于它们各自的模块。

一些全局对象是:

1.  电子竞技
2.  组件
3.  需要
4.  _ _ 文件名
5.  __dirname

以上对象和 require 函数无需导入即可随处访问。

**Process:**Process 对象是一个全局对象，提供关于 node.js process 的信息并对其进行控制。因为它是全局的，所以可以在项目中使用，而无需从任何模块导入它。

它是 EventEmitter 类的一个实例，有许多有用的方法帮助我们更好地了解已经发生的过程以及当前正在经历的过程。

**过程重要事件:**

**beforeExit Event:** 此事件在 Node.js 事件循环被万圣节化且没有安排额外工作之前触发。一般情况下，当没有剩余进程时，Node.js 进程将退出，但是在“beforeExit”上注册的侦听器可以进行异步调用。

## java 描述语言

```js
const process = require('process');

process.on('beforeExit', (data) => {
  console.log('Process beforeExit event with code.');
});

process.on('exit', (data) => {
  console.log('Process exit event with code');
});

console.log('This code is rendered first.');
```

**输出:**

```js
This code is rendered first.
Process beforeExit event with code.
Process exit event with code.
```

**退出事件:**当 Node.js 进程由于以下任一原因即将退出时，会发出“退出”事件:

*   正在显式调用的 process.exit()方法。
*   Node.js 事件循环不再需要执行任何额外的工作。

此时无法阻止事件循环的退出，一旦所有“退出”侦听器都运行完，Node.js 进程将终止。

## java 描述语言

```js
process.on('exit', (data) => {
  console.log(`code execution is goint to end `);
});
```

**输出:**

```js
code execution is goint to end
```

除了以上两个主要事件之外，流程对象还附带了更多的事件。

**Buffer:**node . js 中的 Buffer 类是用来处理原始二进制数据的。每个缓冲区对应于 V8 之外分配的一些原始内存。缓冲区的作用有点像整数数组，但不可调整大小，并且有一大堆专门针对二进制数据的方法。

**创建缓冲区:**

```js
var buffer = Buffer.alloc(6); 
```

*   **输出:**

```js
This will print out 6 bytes of zero
```

```js
var buffer = Buffer.from("Welcome to GeeksforGeeks!", "utf-8");
```

*   **输出:**

```js
This will print out a chain of values in utf-8
```

**写入缓冲区:**如果包含两个参数，第一个参数是数据，第二个参数是编码类型。

```js
buffer.write("GeeksForGeeks", "utf-8")
```

**输出:**

```js
This will print out 13 as size of buffer
```

**读取缓冲区:**我们可以使用 toString()方法读取缓冲区。

## java 描述语言

```js
var buf = Buffer.from('GeeksForGeeks');
console.log(buf.toString());
```

**输出:**

```js
GeeksForGeeks
```