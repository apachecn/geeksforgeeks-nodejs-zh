# 如何解决 Node.js 中未处理的异常？

> 原文:[https://www . geesforgeks . org/如何解决节点中未处理的异常-js/](https://www.geeksforgeeks.org/how-to-resolve-unhandled-exceptions-in-node-js/)

下面讨论了解决 Node.js 中未处理异常的两种方法:

**方法 1:使用 try-catch 块:**我们知道 Node.js 是一个建立在 JavaScript 运行时上的平台，用于轻松构建快速且可扩展的网络应用程序。作为 JavaScript 的一部分，我们知道处理异常最突出的方法是让**尝试并捕捉**块。

**示例:**

```js
try {

    // The synchronous code that
    // we want to catch thrown
    // errors on
    var err = new Error('Hello')
    throw err
} catch (err) {

    // Handle the error safely
    console.log(err)
}
```

**注意:**但是，注意不要在异步代码中使用 try-catch，因为异步抛出的错误不会被捕获。

```js
try {
    setTimeout(function() {
        var err = new Error('Hello')
        throw err
    }, 1000)
}
catch (err) {

    // Example error won't be caught
    // here... crashing our application
    // hence the need for domains
}
```

**方法二:使用流程:**一个好的做法是说，你应该使用**流程**来处理异常。进程是一个提供当前 Node.js 进程信息的全局对象。进程是一个监听函数，它总是在监听事件。
很少有事件是:

*   拆开
*   出口
*   消息
*   多重解析
*   未处理异常情况
*   已处理拒绝
*   未捕获的异常
*   警告

最有效的方法是使用**流程**。如果您的代码流中出现任何未捕获或未处理的异常，该异常将在下面显示的代码中被捕获:

**示例:**

```js
process.on('uncaughtException', function(err) {

    // Handle the error safely
    console.log(err)
})
```

上面的代码将能够处理在 **Node.js** 中发生的任何类型的未处理异常。