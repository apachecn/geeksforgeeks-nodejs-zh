# Node.js 进程退出事件

> 原文:[https://www.geeksforgeeks.org/node-js-process-exit-event/](https://www.geeksforgeeks.org/node-js-process-exit-event/)

**进程**是 Node.js 中的全局对象，它跟踪并包含在机器上特定时间执行的特定 node.js 进程的所有信息。

[process.exit()](https://www.geeksforgeeks.org/node-js-process-exit-method/) 方法是用于结束 Node.js 流程的方法。机器或程序上的每个过程动作都是一个事件。对于每个事件，甚至有一个与特定事件相关联的处理程序，当我们触发特定事件时，它就会执行。为了给事件分配一个事件处理程序，我们在 node.js 中使用了 object.on()方法

**语法:**

```js
process.on("exit", callbackfunction)
```

**参数:**该方法取以下两个参数。

*   **Exit:** is the name of the launch event in the process.
*   [T0】 callback function: 【T1] is the event handler for the event.

**返回类型:**该方法的返回类型为空。

**例 1:**

## index . js

```js
console.log("Starting of the process")

// Binding the event to the eventhandler
process.on('exit',() => {
    console.log("process.exit() method is fired")
})

console.log("Ending of the process")

// Exiting the process
process.exit()
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Starting of the process
Ending of the process
process.exit() method is fired
```

**示例 2:** 在用户定义的事件处理程序中创建进程退出事件处理程序。

## 

```js
// Importing events object
const events = require("events")

console.log("Starting of the process")
const eventEmitter = new events.EventEmitter()

// Initializing
ing event Handler
var Handler = function() {

   // Event handler of exit event
   process.on('exit', () => {
      console.log("process.exit() method is fired")
   })
}

// Bind the  user defined event 
eventEmitter.on("hello",Handler)

// Emit the event
eventEmitter.emit("hello")

console.log("Ending of the process")

// Exiting the process
process.exit()
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Starting of the process
Ending of the process
process.exit() method is fired
```

**参考**:[https://nodejs.org/api/process.html#process_event_exit](https://nodejs.org/api/process.html#process_event_exit)