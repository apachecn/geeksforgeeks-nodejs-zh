# node . js 的本质

> 原文:[https://www.geeksforgeeks.org/essence-of-node-js/](https://www.geeksforgeeks.org/essence-of-node-js/)

Node.js 或 Node 有一个小的核心模块组，通常称为 Node Core，通过使用我们编写的应用程序或我们可以说 Node Core 实现了公共的 Node API，它被公开为公共的 Node API。

节点核心中的一些模块示例如下:

*   为了使用文件系统，我们有一个 **fs** 模块。
*   对于网络，我们有一个 **http** 模块。
*   为了获取特定于操作系统的信息，我们有一个名为**操作系统**的模块。

像这些一样，节点核心中有几十个模块，但它们中的大多数都是为了支持节点的主要用例。节点主要通过**回调**、**事件**和**流**来处理输入输出操作。所以你需要理解这些概念。

在我们开始谈论上述概念之前，请确保您已经安装了 [node.js](https://nodejs.org/en/) 。如果您在安装时遇到问题，可以参考[我们的安装指南](https://www.geeksforgeeks.org/installation-of-node-js-on-windows/)。

**回调:**回调是掌握 Node 需要了解的最重要的基础之一。在此之前，让我们看看为什么我们需要回调，以及回调在 Node 中是如何工作的。

传统 web 服务器同步工作**。这意味着当一个请求被发送到服务器时，服务器处理该请求并提供响应。在处理期间，其他输入/输出操作必须等待当前进程完成，然后只能处理另一个请求。我们称之为阻塞输入/输出，因为新的请求被阻塞，直到当前进程完成。**

**节点有无阻塞 I/O 模型，因为节点在设计上是**异步的**。与传统服务器一样，使用 Node 创建的服务器接收请求、处理请求并返回响应。但是当请求处于处理期间时，节点服务器可以同时执行其他任务。**

****示例:**创建一个新文件夹，然后在其中创建一个 **learn-callback.js** 文件和 **name.txt** 文件。我们的目标是向终端打印定制的 hello 和循环模式。把你的名字放到 **name.txt** 中，保存文件。我们的文件中有“ **GeeksforGeeks** ”。**

*   ****Traditional server’s synchronous version:**

    ```js
    // Tell node we need to work with filesystem
    const fs = require("fs");

    // Read the file contents "synchronously" in
    // string (utf-8) encoding
    const fileContents = fs.readFileSync("name.txt", "utf-8");

    // Print to console
    console.log("Hello, ", fileContents);

    // Print pattern
    for (let i = 0; i < 5; i++) console.log(i);
    ```

    **输出:**

    ```js
    Hello, GeeksforGeeks
    0
    1
    2
    3
    4

    ```** 
*   ****The Node asynchronous version:** Open up your terminal in the directory where your files are saved. Run the code using **node learn-callback.js** and observe the output. you will get to the point but first, see the Node version.

    ```js
    // Tell node we need to work with filesystem
    const fs = require("fs");

    // Read the file contents "asynchronously" in
    // string (utf-8) encoding
    fs.readFile("name.txt", "utf-8", (error, fileContents) => {
        if (error) 
            return error;
        else 
            console.log("Hello, ", fileContents);
    });

    // Print the pattern
    for (let i = 0; i < 5; i++) 
        console.log(i);
    ```

    **输出:**

    ```js
    0
    1
    2
    3
    4
    Hello, GeeksforGeeks

    ```** 

****解释:**使用**节点 learn-callback.js** 运行代码。你注意到输出的不同了吗？这是由于 Node 的非阻塞模型。在**同步**版本中，我们首先观察你好，然后是模式。我们发出读取 **name.txt** 文件的请求，文件被处理，hello 被打印，然后图案被打印。在**同步**模型中，执行是顺序的，即从上到下的顺序。**

**在 node 的**异步**版本中，当我们发出读取文件的请求时，文件开始处理，但是在这种情况下，我们的程序可以在 Node 读取文件的同时执行其他任务。这节省了计算资源，并使节点输入/输出操作极其快速。**

**在上面突出显示的代码中， **fs.readFile** 告诉节点以 utf-8 编码读取 **name.txt** 文件。**的第三个论点是回调。回调是在特定进程完成时执行的函数。当文件被读取时，节点是空闲的，它在 **fs.readFile** 函数之后执行下一行代码，在我们的例子中，这恰好是一个循环，所以循环在读取过程中被执行，我们在终端得到一个模式。当读取完成时，回调函数执行，hello 在模式后被打印在终端中。
因此回调是在进程完成执行后及时执行的函数，在此期间节点可以自由执行其他任务。请记住，回调不是节点的特殊功能。实际上，它们是内置在 JavaScript 中的。节点只是巧妙地利用它来实现无阻塞的输入输出特性。****

****事件:**你可以想想‘X 发生在 Y 身上的时候’这样的事件。所以在这个类比中，“X”是一个由 Node 发出的事件，“Y”是一个等待“X”信号完成其工作的监听器。让我们写一个小程序来把握这个概念。**

*   ****Example:** This example illustrate the Events. Run this code and see if you get the correct output.

    ```js
    // Require "events"; give us access to EventEmitter class
    // EventEmitter class has all the event related methods in it
    const EventEmitter = require("events");

    // Create an instance of the EventEmitter class
    const ourEmitter = new EventEmitter();

    // Create an event listener - listens for the "GfG opened" event
    // Event listeners always keep its ear open; it never sleeps
    // Means it'll keep on listening for the event throughout the code
    // It'll execute the callback function when "GfG opened" event is emitted
    ourEmitter.on("GfG opened", (error) => {
        if (error) 
            return error;
        else 
            console.log("Let's learn computer science concepts.");
    });

    // Emit event or send a signal that "GfG opened" has happened
    ourEmitter.emit("GfG opened");
    ```

    **输出:**

    ```js
    Let's learn computer science concepts.

    ```

    **解释:**当你发出“GfG opened”事件时，我们有一个事件监听器，它执行回调函数，回调函数向控制台打印一条消息。现在让我们看看当我们把**放入我们的发射器时会发生什么。**事件监听器前。** 
*   ****Program where put **ourEmitter.emit(“GfG opened”);** before the event listener:**

    ```js
    ...
    // Emit "GfG opened"
    ourEmitter.emit("GfG opened");

    // Create an event listener
    ourEmitter.on("GfG opened", (error) => {
        if (error) 
            return error;
        else 
            console.log("Let's learn computer science concepts.");
    ...
    ```

    **输出:**节点事件 API 表示:

    ```js
    "When the EventEmitter object emits an event, all of the functions attached to 
    that specific event are called synchronously"
    ```

    这意味着当节点发出“GfG opened”事件时，节点会检查是否有人在监听这个事件，但是节点还不知道监听程序，因为监听程序是在发出命令之后。节点事件`.emit`命令无法检查在发出命令后出现的监听器，因为它是*同步的*。所以在处理事件时，代码的顺序很重要。经验法则是:先听后发。首先，创建一个侦听器，然后发出事件。

    事件对于创建游戏服务器非常有用，游戏服务器需要知道新玩家何时连接或断开、移动、射击、死亡等。此外，事件大量用于创建聊天室，您可以在其中向听众广播消息。

    **流:**读写数据有两种方式:**缓冲**和**流**。在缓冲方法中，必须先读取全部数据，然后才能开始写入过程。但是这些溪流效率更高。流读取一个数据块，此时另一个流可以继续写入前一个数据块。所以 node.js 异步处理数据**-并行完成任务**。

    溪流有管道。基本上，管道的作用是获取一个流的输出，该输出可以通过管道发送到另一个流，成为新流的输入。这给了节点惊人的力量。流是有时间效率的，因为它们不会浪费时间等待所有的阅读同时发生，而是我们不断地同时阅读和写作。是的，正如他们所说，我们正在异步地做这件事。

    此外，流是空间高效的(节省内存空间)。假设我们必须读取一个 100 兆的文件并将其写入某个地方，我们有一个 50 兆的缓冲区。缓冲方法首先需要读取整个数据，然后才能开始写入。使用缓冲方法，当读取过程开始时，一旦超过 50 MB 标记，我们的缓冲区最终就会泄漏。

    但是我们可以使用流来读取 50 MB 的数据块，写入该数据，然后在继续读取下一个 50 MB 之前清除该缓冲区。所以 stream 的案子不会有漏洞。**