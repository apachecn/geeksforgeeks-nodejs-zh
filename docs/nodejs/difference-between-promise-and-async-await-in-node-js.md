# node . js 中承诺和异步等待的区别

> 原文:[https://www . geesforgeks . org/node-js 中的承诺和异步等待之间的区别/](https://www.geeksforgeeks.org/difference-between-promise-and-async-await-in-node-js/)

在 NodeJS 或 JavaScript 中有不同的处理操作的方法。对于异步执行，不同的进程同时运行，并在每个进程的结果可用时进行处理。在 NodeJS 或 JavaScript 中有不同的方法来处理异步代码，它们是:

*   [回调](https://www.geeksforgeeks.org/node-js-callback-concept/)
*   [承诺](https://www.geeksforgeeks.org/promises-in-node-js/)
*   [异步/等待](https://www.geeksforgeeks.org/using-async-await-in-node-js/)

**1。承诺:**

节点中的承诺类似于现实生活中的承诺。这是一定会有所作为的保证。Promise 用于跟踪异步事件是否已经执行，并确定事件发生后会发生什么。它是一个具有 3 种状态的物体，即:

*   **待定:**初始状态，事件发生前。
*   **已解决:**操作成功完成后。
*   **拒绝:**如果操作在执行过程中出现错误，则承诺失败。

**示例:**向数据库服务器请求数据时，Promise 处于挂起状态，直到收到数据。如果数据接收成功，则承诺处于已解决状态，如果数据无法成功接收，则承诺处于拒绝状态。

**承诺的错误处理:**对于成功解决的承诺，我们使用。然后()方法而对于被拒绝的承诺，我们用。catch()方法。使用处理承诺后运行代码。然后()或。catch()方法，我们可以。finally()方法。里面的代码。finally()方法运行一次，而不管承诺的状态如何。

**示例:**

## java 描述语言

```
<script>
  const promise = new Promise(function (resolve, reject) {
    const string1 = "geeksforgeeks";
    const string2 = "geeksforgeeks";
    if (string1 === string2) {
      resolve();
    } else {
      reject();
    }
  });

  promise
    .then(function () {
      console.log("Promise resolved successfully");
    })
    .catch(function () {
      console.log("Promise is rejected");
    });
</script>
```

**输出:**

```
Promise resolved successfully
```

**2。异步/等待:**

异步/等待用于处理异步函数中的承诺。它基本上是承诺的语法糖。它只是重新设计代码的包装器，并使承诺更容易阅读和使用。它使异步代码看起来更像同步/过程代码，更容易理解。

wait 只能在异步函数中使用。它用于调用异步函数，并等待它解析或拒绝。wait 阻止代码在其所在的异步函数中执行。

**Aysnc/Await 中的错误处理:**对于成功解决的承诺，我们使用 try，对于被拒绝的承诺，我们使用 catch。要在使用 try 或 catch 处理完承诺后运行代码，我们可以。finally()方法。里面的代码。finally()方法运行一次，而不管承诺的状态如何。

**示例:**

## java 描述语言

```
<script>
  const helperPromise = function () {
    const promise = new Promise(function (resolve, reject) {
      const x = "geeksforgeeks";
      const y = "geeksforgeeks";
      if (x === y) {
        resolve("Strings are same");
      } else {
        reject("Strings are not same");
      }
    });

    return promise;
  };

  async function demoPromise() {
    try {
      let message = await helperPromise();
      console.log(message);
    } catch (error) {
      console.log("Error: " + error);
    }
  }

  demoPromise();
</script>
```

**输出:**

```
Strings are same
```

**许诺与异步/等待的区别:**

<figure class="table">

| **先生。否〔t1〕** | **许诺** | **异步/等待** |
| **1 .** | Promise is an object that represents the intermediate state of an operation, and it is guaranteed to be completed at some future time. | Async/Await is a promised grammar sugar, and a wrapper makes code execution more synchronous. |
| **2 .** | There are three states of commitment-resolved, rejected and pending. | It has no state. It returns a promise, either solved or rejected. |
| **3 .** | If the function "fxn1" is to be executed after promise, promise.then(fxn1) continues to execute the current function after adding the fxn1 call to the callback chain. | If the function "fxn1" is to be executed after await, then await X () pauses the execution of the current function and then executes fxn1. |
| **4 .** | Error handling usage completed. Then () and. Catch () method. | Error handling usage completed. Try () and. Catch () method. |
| **5 .** | Commitment chains can sometimes become difficult to understand. | Compared with the commitment chain, it is easier to read and understand the program flow by using asynchrony/wait. |

</figure>