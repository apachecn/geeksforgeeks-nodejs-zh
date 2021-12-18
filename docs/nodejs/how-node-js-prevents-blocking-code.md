# node . js 如何防止代码阻塞？

> 原文:[https://www . geesforgeks . org/how-node-js-prevent-blocking-code/](https://www.geeksforgeeks.org/how-node-js-prevents-blocking-code/)

[<u>Node.js</u>](https://www.geeksforgeeks.org/introduction-to-nodejs/) 是一个跨平台的 [<u>JavaScript</u>](https://www.geeksforgeeks.org/javascript-tutorial/) 运行时环境，有助于执行和实现服务器端程序。假设节点通过使用单线程事件循环来防止阻塞代码。在本文中，我们将讨论这个事件循环以及它如何通过使用回调异步实现函数。

**阻塞和非阻塞操作:**阻塞操作是指阻止其他代码执行直到完成的代码段。而非阻塞操作允许执行更多的代码片段，而无需等待并在完成后使用回调。

因此，可以说阻塞代码同步工作，而非阻塞代码异步工作。在讨论非阻塞代码时，我们提出了一个术语，叫做回调。回调是一个函数，当一个进程完成它的执行并想用外部函数继续它的正常执行时被调用。

**节点和事件循环:**现在我们知道什么是阻塞和非阻塞操作，我们可以讨论节点如何防止阻塞代码。节点使用单个线程，这意味着一次可以执行一个任务。这是通过使用堆栈来完成的。从上到下读取代码时，每个指令都被推入堆栈，当执行完成时，它会从堆栈中弹出。现在，我们可能会遇到一个执行时间较长的指令/函数，这可能会导致弹出堆栈和执行更多语句的延迟。

所以 Node.js 允许的是使用**事件循环**。每当我们遇到这种情况时，导致延迟的进程就会从堆栈中卸载，该进程的执行会继续并行执行主代码。因此，该函数的回调被推入任务队列，代码继续异步执行。当进程完成执行时，回调函数从该进程返回所需的输出，并恢复正常执行。

**示例:**让我们考虑一个演示事件循环如何工作的示例。

T4T6

```
<script>

// Simple JavaScript Code to show Event
// loop demonstration for Node
console.log("Geeks");

// Printing Geeks after 3 seconds
setTimeout(function cb() {
    console.log("Geeks");
}, 3000);

console.log("For");
</script>
```

T7

使用以下命令运行 **index.js** 文件。

**输出:**

```
Geeks
For
Geeks
```

**说明:**虽然登录 ***极客*** 的指令在登录 ***的指令之前，但对于*** 来说，这并不是他们登录控制台的顺序。发生的情况是当调用 *setTimeout* 功能时，触发等待 3 秒的定时器。但是，当函数在调用堆栈中时，这种超时不会发生，而是由节点应用编程接口处理。因此，进一步的指令得到应有的处理，当计时器归零时，回调函数将被调用，函数的结果将被返回。

**参考文献:**T2】https://nodejs.org/en/docs/guides/blocking-vs-non-blocking/