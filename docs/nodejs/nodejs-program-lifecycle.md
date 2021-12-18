# 节点程序生命周期

> 原文:[https://www.geeksforgeeks.org/nodejs-program-lifecycle/](https://www.geeksforgeeks.org/nodejs-program-lifecycle/)

[Node.js](https://www.geeksforgeeks.org/introduction-to-nodejs/) 是一个 JavaScript 运行时，构建在 Chrome 的 V8 JavaScript 引擎上，它的运行时环境包括了我们执行用 JavaScript 编写的程序所需的一切。它使用事件驱动的非阻塞输入/输出模型，这使得它最具可扩展性和受欢迎。非阻塞仅仅意味着可以并行处理多个请求。

**node . js 程序的生命周期:**为了理解它的生命周期，你必须熟悉事件循环。事件循环可以让你的任务变得非常快，还可以执行多任务。它允许 Node.js 执行非阻塞的输入/输出操作。您可以在这里了解更多关于事件循环[的信息。当您使用 node app.js 运行节点文件时，脚本开始执行。解析器将它解析成机器语言，这意味着所有的函数和变量都注册在一个内存位置。在解析完代码后，我们的程序将不会退出，并运行无限次数，这是可能的，因为事件循环。一旦事件循环开始执行，只要注册了事件侦听器，它就会运行。](https://www.geeksforgeeks.org/node-js-event-loop/)

**示例:**您拥有数据库，并且必须从数据库中访问数据，或者您想要向数据库中插入一些只需要调用一些函数的东西，因此当您调用它们时，将花费一些时间(可能是纳秒或微秒，但这将花费一些时间)，因此不可能对于每个请求，我们都可以等待那个特定的时间，然后我们继续下一个请求，因此这就是事件循环进入画面的地方。您的数据库部分将在后台运行，事件循环将持续运行，这样它也可以处理对另一个请求的需求。这将在 node.js 中的单个线程上完成。您也可以使用 **process.exit()** 显式退出循环。

## java 描述语言

```js
const http = require('http');
const server = http.createServer(function (req, res) {

console.log("server is running");
process.exit();

});

server.listen(8000);
```

**说明:**在上面的 **createServer()方法**里面的程序中，你已经简单的写了流程..exit()因此，一旦您使用 node app 运行此程序，您的服务器将等待侦听您的请求，一旦您向它提供请求，它将从事件循环中退出。通过调用这个函数，Node.js 将强制当前正在运行的进程尽快中止，如果有任何异步操作发生，它们也将被立即终止。

**定时器:**node . js 中的定时器模块由帮助控制代码执行时间的函数组成。它包括 setTimeout()、setImmediate()和 setInterval()方法。

*   **[setTimeout()方法:](https://www.geeksforgeeks.org/java-script-settimeout-setinterval-method/)**setTimeout()方法用于在指定的毫秒数后调度代码执行。指定的函数将被执行一次。我们可以使用 clearTimeout()方法来阻止函数运行。setTimeout()方法返回可以在 clearTimeout()方法中使用的 ID。

    ## 爪哇描述语言

    ```js
    let str = 'GeeksforGeeks!'; 

    setTimeout(function () { 
        return console.log(str); 
    }, 5000); 

    // This console log is executed right away 
    console.log('Executing setTimeout() method'); 
    ```

*   **setImmediate()方法:**setImmediate()方法用于在当前事件循环周期结束时执行代码。任何作为 setImmediate()参数传递的函数都是回调函数，可以在事件循环的下一次迭代中执行。

    ## 爪哇描述语言

    ```js
    let str = 'GeeksforGeeks!'; 

    setImmediate(function () { 
        return console.log(str); 
    }); 

    // This console log is executed right away 
    console.log('Executing setImmediate() method'); 
    ```

*   **[setInterval()方法](https://www.geeksforgeeks.org/java-script-settimeout-setinterval-method/):**setInterval()方法用于以指定的时间间隔(以毫秒为单位)调用函数。它仅用于在指定时间段后执行一次该功能。
    我们可以使用 clearInterval()方法来阻止函数运行。setInterval()方法返回可在 clearInterval()方法中使用的 ID。

    ## java 描述语言

    ```js
    let str = 'GeeksforGeeks!'; 

    setInterval(function() { 
        return console.log(str); 
    }, 5000); 

    // This console log is executed right away 
    console.log('Executing setInterval() method'); 
    ```

在 Node.js [中了解更多关于定时器的信息，点击这里](https://www.geeksforgeeks.org/what-are-the-various-timing-features-of-node-js/)。

**process.nextTick(回调)方法:**每当一个新的操作队列被初始化时，我们可以把它看作一个新的 Tick。process.nextTick()方法将回调函数添加到下一个事件队列的开头。需要注意的是，在程序进程开始时，在事件循环被处理之前，第一次调用 nextTick()方法。

> 计时器–>等待回调–>空闲、准备–>连接(轮询、数据等)–>检查–>关闭回调