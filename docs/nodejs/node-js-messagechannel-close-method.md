# Node.js MessageChannel.close()方法

> 原文:[https://www . geesforgeks . org/node-js-messagechannel-close-method/](https://www.geeksforgeeks.org/node-js-messagechannel-close-method/)

**MessageChannel.close()** 方法是 **worker_threads** 模块中 Worker 类的内置应用编程接口，用于禁用消息端口的对象以发送进一步的消息。

**语法:**

```
const MessageChannel.close()
```

**参数:**此方法不接受任何参数。

**返回值:**此方法不返回值。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// MessageChannel.close() method

// Importing worker_thread module
const { MessageChannel, receiveMessageOnPort }
        = require('worker_threads');

// Creating and initializing the MessageChannel
const { port1, port2} = new MessageChannel();

// Posting data in port1
port1.postMessage({ hello: 'world1' });

// Posting data in port2
port2.postMessage({ hello: 'world2' });

/// Display the result
console.log("received data in port1 : ");
console.log( receiveMessageOnPort(port1));
console.log("received data in port2 : ");
console.log( receiveMessageOnPort(port2));

// Closing the ports
port1.close();
port2.close();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
received data in port1 :
{ message: { hello: 'world2' } }
received data in port2 :
{ message: { hello: 'world1' } }
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// MessageChannel.close() Method

// Importing worker_thread module
const { MessageChannel, receiveMessageOnPort }
        = require('worker_threads');

// Creating and initializing the MessageChannel
const { port1, port2} = new MessageChannel();

// Catching the event message
port2.on('message', (message) => console.log(message));

// Catching the event close
port2.on('close', () => console.log('closed!'));

// Sending message to port2
port1.postMessage('GFG');

// Closing port by using close() method
port1.close();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
GFG
closed!
```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/worker _ threads . html # worker _ threads _ port _ close](https://nodejs.org/dist/latest-v12.x/docs/api/worker_threads.html#worker_threads_port_close)