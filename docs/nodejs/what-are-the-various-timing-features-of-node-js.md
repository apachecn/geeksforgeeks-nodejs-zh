# node . js 的各种时序特性有哪些？

> 原文:[https://www . geesforgeks . org/节点的各种时序特征是什么-js/](https://www.geeksforgeeks.org/what-are-the-various-timing-features-of-node-js/)

Node.js 中的计时器模块由帮助控制代码执行时间的函数组成。它包括 **setTimeout()、setImmediate()、**和 **setInterval()** 方法。

**1。setTimeout()方法:**setTimeout()方法用于在指定的毫秒数后调度代码执行。指定的函数将被执行一次。我们可以使用 clearTimeout()方法来阻止函数运行。setTimeout()方法返回可以在 clearTimeout()方法中使用的 ID。

**语法:**

```
setTimeout(callback, delay, args )
```

**参数:**

*   **回调:**此参数保存要执行的函数。
*   **延迟:**此参数保存调用回调函数前等待的毫秒数。
*   **参数:**该参数保存可选参数。

**示例:**

```
let str = 'GeeksforGeeks!';

setTimeout(function () {
    return console.log(str);
}, 5000);

// This console log is executed right away
console.log('Executing setTimeout() method');
```

**输出:**

```
Executing setTimeout() method
GeeksforGeeks!
```

请注意，控制台首先执行。实现的诀窍是，代码只保证在至少经过这段时间后执行。

**2。setImmediate()方法:**setImmediate()方法用于在当前事件循环周期结束时执行代码。任何作为 setImmediate()参数传递的函数都是回调函数，可以在事件循环的下一次迭代中执行。

**语法:**

```
setImmediate(callback, args)
```

**参数:**

*   **回调:**此参数保存在 Node.js 事件循环的这一轮结束时要调用的函数。
*   **参数:**此参数保存函数的可选参数。

**示例:**

```
setTimeout(function () {
    console.log('setTimeout() function running');
}, 5000);

// An interval
setInterval(function () {
    console.log('setInterval() function running');
}, 5000);

// An immediate, its callback will be 
// executed before those defined above
setImmediate(function () {
    console.log('setImmediate() function running');
});

// IO callbacks and code in the normal
// event loop runs before the timers
console.log('Simple statement in the event loop');
```

**输出:**

```
Simple statement in the event loop
setImmediate() function running
setTimeout() function running
setInterval() function running
setInterval() function running
setInterval() function running
setInterval() function running
. . .
```

请注意，即使 setImmediate 函数是在 setTimeout 和 setInterval 函数之后定义的，它也是在它们之前运行的。

**3。setInterval()方法:**setInterval()方法用于以指定的时间间隔(以毫秒为单位)调用函数。它仅用于在指定时间段后执行一次该功能。
我们可以使用 clearInterval()方法来阻止函数运行。setInterval()方法返回可在 clearInterval()方法中使用的 ID。

**语法:**

```
setInterval(callback, delay, args)
```

**参数:**

*   **回调:**该参数保存定时器到时要调用的函数。
*   **延迟:**此参数保存调用 vallback 函数之前等待的毫秒数。
*   **参数:**此参数保存函数的可选参数。

**示例:**

```
setInterval(function() {
    console.log('Welcome to GeeksforGeeks');
}, 5000);
```

**输出:**

```
Welcome to GeeksforGeeks
Welcome to GeeksforGeeks
.....
```

它将多次打印输出，时间间隔为 5 秒。