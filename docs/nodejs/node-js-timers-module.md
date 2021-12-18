# Node.js 定时器模块

> 原文:[https://www.geeksforgeeks.org/node-js-timers-module/](https://www.geeksforgeeks.org/node-js-timers-module/)

Node.js 中的 **Timers** 模块包含各种功能，允许我们在一段设定的时间后执行一段代码或一个函数。计时器模块是全局的，我们不需要使用 require()来导入它。

**定时器模块具有以下功能:**

1.  **调度定时器:**用于在设定的时间段后调用一个函数。
    *   setImmediate()
    *   setInterval()
    *   setTimeout()
2.  **取消定时器:**用于取消预定定时器。
    *   clearImmediate()
    *   clearInterval()
    *   clearTimeout()

**1。setImmediate()方法:**它调度 I/O 事件回调后回调的“立即”执行。在下面的示例中，调用了多个 setImmediate 函数。每当我们这样做的时候，这些回调函数都会按照它们被创建的顺序排队等待执行。在每次事件循环迭代之后，整个回调队列都会被处理。如果立即计时器从正在执行的回调中排队，则该计时器直到下一次事件循环迭代才会被触发。

```js
setImmediate(function A() {
    setImmediate(function B() {
      console.log(1);
      setImmediate(function D() { 
        console.log(2);
      });
    });

    setImmediate(function C() {
      console.log(3);
      setImmediate(function E() { 
        console.log(4);
      });
    });
});

console.log('Started...');
```

**输出:**

```js
Started...
1
3
2
4

```

在上面的例子中，在事件循环的第一次迭代中，函数 A 被激发。然后在第二次迭代中激发函数 B，在第三次迭代中激发函数 C。类似地，函数 D 和 E 分别在第四次和第五次迭代中触发。

**2。setInterval()方法:**它在作为参数传递的每 t 次(以毫秒为单位)后重复回调的执行。

```js
// Executed after every 1000 milliseconds
// from the start of the program
setInterval(function A() {
    return console.log('Hello World!');
}, 1000);

// Executed right away
console.log('Executed before A...');
```

**输出:**

```js
Executed before A...
Hello World!
Hello World!
Hello World!
Hello World!
Hello World!
...

```

**3。setTimeout()方法:**它调度回调在某个时间(以毫秒为单位)后的执行，该时间作为参数传递。

```js
// Executed after 3000 milliseconds 
// from the start of the program
setTimeout(function A() {
    return console.log('Hello World!');
}, 3000);

// executed right away
console.log('Executed before A...');
```

**输出:**

```js
Executed before A...
Hello World!

```

**4。clearImmediate()方法:**用于简单取消 setImmediate()方法创建的 Immediate 对象。

```js
var si = setImmediate(function A() {
    console.log(1);
});

// clears setInterval si
clearImmediate(si);

console.log(2);
```

**输出:**

```js
2
```

**5。clearInterval()方法:**用于取消 setInterval()方法创建的立即对象。

```js
var si = setInterval(function A() {
    return console.log("Hello World!");
}, 500);

setTimeout(function() {
    clearInterval(si);
}, 2000);
```

clearInterval()在 500 ms 后清除 setInterval 'si '，然后函数 A 执行四次。

**输出:**

```js
Hello World!
Hello World!
Hello World!
Hello World!

```

**6。clearTimeout()方法:**用于取消 setTimeout()方法创建的 Immediate 对象。

```js
// si1 is cleared by clearTimeout()
var si1 = setTimeout(function A() {
    return console.log("Hello World!");
}, 3000);

// only si2 is executed
var si2 = setTimeout(function B() {
    return console.log("Hello Geeks!");
}, 3000);

clearTimeout(si1);
```

当 clearTimeout()方法清除“si1”时，只执行 setInterval“si2”。
**输出:**

```js
Hello Geeks!

```