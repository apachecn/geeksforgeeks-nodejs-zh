# Node.js process.disconnect()方法

> 原文:[https://www . geesforgeks . org/node-js-process-disconnect-method/](https://www.geeksforgeeks.org/node-js-process-disconnect-method/)

**process.disconnect()** 属性是进程模块的内置应用程序编程接口，子进程使用该接口来断开与父进程的连接。此方法不适用于根进程，因为它没有任何父进程。

**语法:**

```js
process.disconnect()
```

**参数:**不取任何参数。

**返回值:**没有返回值。

**示例 1:** 在 Parent.js 中，我们生成子进程。在 Child.js 中，我们在 Child.js 中得到消息*。然后如果*进程连接*为真，则在控制台上打印一条消息并断开连接。*

 *## 亲子

```js
// Require fork method from child_process 
// to spawn child process
const fork = require('child_process').fork;

// Child process file
const child_file = 'Child.js';

// Spawn child process
const child = fork(child_file);
```* 

## *亲子*

 *```js
console.log('In Child.js')

// If the send method is available
if (process.connected) {

    // Check if its connected or not
    if (process.connected == true) {
        console.log("Child.js is connected.");
    }

    // Use process.disconnect() to disconnect
    process.disconnect();

    // Check if its connected or not
    if (process.connected == false) {
        console.log("Child.js has been disconnected.");
    }
}
```* 

*使用以下命令运行**父. js**:*

```js
*node Parent.js*
```

***输出:***

```js
*In Child.js
Child.js is connected.
Child.js has been disconnected.*
```

***例 2:** 一段时间后断开。请注意，断开功能运行后，不会打印任何消息。*

 *## 亲子

```js
// Require fork method from child_process 
// to spawn child process
const fork = require('child_process').fork;

// Child process file
const child_file = 'Child.js';

// Spawn child process
const child = fork(child_file);
```* 

## *亲子*

 *```js
console.log('In Child.js')

// If the send method is available
if (process.connected) {

    // Send multiple messages
    setTimeout((function () {
        if (process.connected == true) {
            console.log("This was sent after 1 second.");
        }
    }), 1000);

    setTimeout((function () {
        if (process.connected == true) {
            console.log("This was sent after 2 seconds.");
        }
    }), 2000);

    // Disconnect after 2.5 seconds
    setTimeout((function () {
        process.disconnect();
    }), 2500);

    setTimeout((function () {
        if (process.connected == true) {
            console.log("This was sent after 3 seconds.");
        }
    }), 3000);
}
```* 

*使用以下命令运行**父. js**:*

```js
*node Parent.js*
```

***输出:***

```js
*In Child.js
Message from child: This was sent after 1 second.
Message from child: This was sent after 2 seconds.*
```

***参考:**[https://nodejs . org/API/process . html # process _ process _ disconnect](https://nodejs.org/api/process.html#process_process_disconnect)*