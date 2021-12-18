# node . js messagechannel . postmessage()方法

> 原文:[https://www . geesforgeks . org/node-js-message channel-postmessage-method/](https://www.geeksforgeeks.org/node-js-messagechannel-postmessage-method/)

**messageport . postmessage()**方法是 **worker_threads** 模块中 Worker 类的内置应用编程接口，用于将消息从一个端口发送到另一个端口。

**语法:**

```js
const MessagePort.postMessage(value[, transferList])
```

**参数:**该方法以值为参数，可以包含任意一种对象。

**返回值:**此方法将消息从一个端口发送到另一个端口。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// MessageChannel.postMessage() method

// Importing worker_thread module
const { MessageChannel, receiveMessageOnPort }
        = require('worker_threads');

// Creating and initializing the MessageChannel
const { port1, port2 } = new MessageChannel();

// Sending data to port 2
// by using postMessage() method
port1.postMessage({ hello: 'world1' });

// Posting data in port 1
// by using postMessage() method
port2.postMessage({ hello: 'world2' });

/// Display the result
console.log("received data in port1 : ");
console.log(receiveMessageOnPort(port1));

console.log("received data in port2 : ");
console.log(receiveMessageOnPort(port2));

// Closing the ports
port1.close();
port2.close();
```

**输出:**

```js
received data in port1 :
{ message: { hello: 'world2' } }
received data in port2 :
{ message: { hello: 'world1' } }
```

**示例 2:** **文件名:index . js**

## Javascript

```js
// Node.js program to demonstrate the
// MessageChannel.postMessage() method

// Importing worker_thread module

const { MessageChannel, receiveMessageOnPort }
        = require('worker_threads');

// Creating and initializing the MessageChannel
const { port1, port2 } = new MessageChannel();

// Catching the event message
port2.on('message', (message) => console.log(message));

// Catching the event close
port2.on('close', () => console.log('closed!'));

// Sending message to port2
// by using postMessage() method
port1.postMessage('GFG');

// Closing port by using
// close() method
port1.close();
```

**输出:**

```js
GFG
closed!
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/worker _ threads . html # worker _ threads _ port _ postmessage _ value _ transfer list](https://nodejs.org/dist/latest-v12.x/docs/api/worker_threads.html#worker_threads_port_postmessage_value_transferlist)