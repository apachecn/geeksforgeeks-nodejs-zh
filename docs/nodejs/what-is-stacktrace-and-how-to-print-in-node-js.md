# 什么是 stacktrace，如何在 node.js 中打印？

> 原文:[https://www . geeksforgeeks . org/什么是 stacktrace 和如何在节点中打印-js/](https://www.geeksforgeeks.org/what-is-stacktrace-and-how-to-print-in-node-js/)

Node.js 是一个开源项目，可以用于服务器端脚本。Node.js 是一个跨平台的工具，它允许开发人员在不担心运行时环境的情况下进行编码。Node.js 广泛用于构建动态、轻量级和可扩展的 web 应用程序。Node.js 提供了一个可以用于前端和后端开发的 JavaScript 运行时环境。然而，应用程序经常抛出必须处理的错误或异常。

JVM 会自动显示一个堆栈跟踪，指示在程序执行过程中发生了错误。堆栈跟踪用于在程序执行期间跟踪特定实例上的活动堆栈帧。调试代码时，堆栈跟踪很有用，因为它显示了导致错误的确切点。Node.js 中的错误可以分为四大类:

*   标准的 JavaScript 错误
*   系统错误
*   用户指定的错误
*   断言错误

Node.js 支持几种机制来传播和处理程序执行过程中出现的错误。所有标准的 JavaScript 错误都会通过抛出一个可以在堆栈跟踪中查看的错误来立即处理。

在 Node.js 中有四种打印堆栈跟踪的方法，它们是:

*   **Using error.stack Property:** The error.stack property describes the point in the code at which the Error was instantiated.

    **语法:**

    ```js
    error.stack
    ```

    **示例:**

    ```js
    console.log("This program demonstrates "
                + "stack trace in Node.js");
    var err = new Error().stack
    console.log(err);
    ```

    **输出:**

    ```js
    This program demonstrates stack trace in Node.js
    Error
        at Object. (/home/cg/root/2523129/main.js:20:11)
        at Module._compile (module.js:570:32)
        at Object.Module._extensions..js (module.js:579:10)
        at Module.load (module.js:487:32)
        at tryModuleLoad (module.js:446:12)
        at Function.Module._load (module.js:438:3)
        at Module.runMain (module.js:604:10)
        at run (bootstrap_node.js:389:7)
        at startup (bootstrap_node.js:149:9)
        at bootstrap_node.js:504:3

    ```

*   **Using Error.captureStackTrace() Method:** This method creates a .stack property on obj that returns a string representing the point in the code at which Error.captureStackTrace(obj) was called. The func parameter represents a function which is optional.

    **语法:**
    **错误. captureStackTrace(obj，func)**

    **示例:**

    ```js
    const obj = {};
    Error.captureStackTrace(obj);
    console.log(obj.stack);

    // Alternatively
    function MyNewError() {
        Error.captureStackTrace(this, MyNewError);
    }

    console.log(new MyNewError().stack);
    ```

    **输出:**

    ```js
    Error
        at Object. (/home/cg/root/2523129/main.js:25:13)
        at Module._compile (module.js:570:32)
        at Object.Module._extensions..js (module.js:579:10)
        at Module.load (module.js:487:32)
        at tryModuleLoad (module.js:446:12)
        at Function.Module._load (module.js:438:3)
        at Module.runMain (module.js:604:10)
        at run (bootstrap_node.js:389:7)
        at startup (bootstrap_node.js:149:9)
        at bootstrap_node.js:504:3

    ```

*   **Using try-catch block:** It is a mechanism of Error Handling and it is used when a piece of code is surrounded in a try block and throw an error to the catch block. If the error is not handled then the program terminates abruptly.

    **示例:**

    ```js
    try {
        throw new Error("Error occurred");  
    }
    catch(e) {
        console.log(e);
    }
    ```

    **输出:**

    ```js
    Error
        at Object. (/home/cg/root/2523129/main.js:25:13)
        at Module._compile (module.js:570:32)
        at Object.Module._extensions..js (module.js:579:10)
        at Module.load (module.js:487:32)
        at tryModuleLoad (module.js:446:12)
        at Function.Module._load (module.js:438:3)
        at Module.runMain (module.js:604:10)
        at run (bootstrap_node.js:389:7)
        at startup (bootstrap_node.js:149:9)
        at bootstrap_node.js:504:3

    ```

*   **Using trace command:** The console.trace() method is used to display the trace which represents how the code ended up at a certain point.

    **示例:**

    ```js
    console.trace("hello world");
    ```

    **输出:**

    ```js
    Trace: hello world
        at Object. (/home/cg/root/2523129/main.js:28:9)
        at Module._compile (module.js:570:32)
        at Object.Module._extensions..js (module.js:579:10)
        at Module.load (module.js:487:32)
        at tryModuleLoad (module.js:446:12)
        at Function.Module._load (module.js:438:3)
        at Module.runMain (module.js:604:10)
        at run (bootstrap_node.js:389:7)
        at startup (bootstrap_node.js:149:9)
        at bootstrap_node.js:504:3

    ```