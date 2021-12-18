# node . js event emitter

> 原文:[https://www.geeksforgeeks.org/node-js-eventemitter/](https://www.geeksforgeeks.org/node-js-eventemitter/)

Node.js 使用事件模块来创建和处理自定义事件。事件发射器类可用于创建和处理自定义事件模块。
导入事件模块的语法如下:

**语法:**

```
const EventEmitter = require('events');
```

添加新侦听器时，所有事件发射器都会发出事件**新侦听器**，删除现有侦听器时，所有事件发射器都会发出事件**删除侦听器**。它还提供了另一个选项:

**布尔捕获拒绝**

```
Default Value: false
It automatically captures rejections.
```

**监听事件:**在发出任何事件之前，它必须注册函数(回调)来监听事件。

**语法:**

```
eventEmitter.addListener(event, listener)
eventEmitter.on(event, listener)
```

**eventEmitter.on(事件，监听器)**和 **eventEmitter.addListener(事件，监听器)**非常相似。它在指定事件的侦听器数组末尾添加侦听器。对同一个事件和侦听器的多次调用将多次添加侦听器，并相应地激发多次。这两个函数都返回发射器，所以调用可以被链接。

**发射事件:**每个事件在 nodejs 中都被命名为事件。我们可以通过 emit(event，[arg1]，[arg2]，[…])函数触发一个事件。我们可以向侦听器函数传递任意一组参数。

**语法:**

```
eventEmitter.emit(event, [arg1], [arg2], [...])

```

**示例:**

```
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter = new EventEmitter();

// Registering to myEvent 
eventEmitter.on('myEvent', (msg) => {
   console.log(msg);
});

// Triggering myEvent
eventEmitter.emit('myEvent', "First event");
```

**输出:**

```
First event
```

**移除侦听器:****事件发射器.移除侦听器()**获取两个参数事件和侦听器，并从订阅该事件的侦听器数组中移除该侦听器。而**event emitter . removeall listeners()**从数组中移除订阅了所述事件的所有侦听器。

**语法:**

```
eventEmitter.removeListener(event, listener)
eventEmitter.removeAllListeners([event])
```

**示例:**

```
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter = new EventEmitter();

var geek1= (msg) => {
    console.log("Message from geek1: " + msg);
};

var geek2 = (msg) => {
    console.log("Message from geek2: " + msg);
};

// Registering geek1 and geek2
eventEmitter.on('myEvent', geek1);
eventEmitter.on('myEvent', geek1);
eventEmitter.on('myEvent', geek2);

// Removing listener geek1 that was
// registered on the line 13
eventEmitter.removeListener('myEvent', geek1);

// Triggering myEvent
eventEmitter.emit('myEvent', "Event occurred");

// Removing all the listeners to myEvent
eventEmitter.removeAllListeners('myEvent');

// Triggering myEvent
eventEmitter.emit('myEvent', "Event occurred");
```

**输出:**

```
Message from geek1: Event occurred
Message from geek2: Event occurred

```

我们注册了两次 geek1 和一次 geek2。为了调用 event emitter . removelistener(' myEvent '，geek1)，将删除 geek1 的一个实例。最后，通过使用 removeAllListeners()方法移除所有侦听器，该方法将移除 myEvent 的所有侦听器。

**特殊事件:**当添加新的监听器和移除**【移除监听器】**现有监听器时，所有事件发射器实例都会发出事件**【新监听器】**。

*   **事件:“newListener”**事件发射器实例将在侦听器添加到其内部侦听器数组之前发出自己的“newListener”事件。为“newListener”事件注册的侦听器将被传递给正在添加的侦听器的事件名称和引用。在将侦听器添加到数组之前，会触发事件“newListener”。

    ```
    eventEmitter.once( 'newListener', listener)
    eventEmitter.on( 'newListener', listener)
    ```

*   **事件:“移除监听器”****“移除监听器”**事件在监听器被移除后发出。

    ```
    eventEmitter.once( ‘removeListener’, listener)
    eventEmitter.on( 'removeListener’, listener)
    ```

*   **事件:“错误”**当事件发射器实例中发生错误时，典型的操作是发出**“错误”**事件。如果事件发射器没有为“错误”事件注册至少一个侦听器，并且发出了“错误”事件，则会引发错误，打印堆栈跟踪，并退出 Node.js 进程。

    ```
    eventEmitter.on('error', listener)

    ```

**示例:**

```
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter = new EventEmitter();

// Register to error
eventEmitter.on('error', (err) => {
    console.error('Attention! There was an error');
});

// Register to newListener
eventEmitter.on( 'newListener', (event, listener) => {
    console.log(`The listener is added to ${event}`);
});

// Register to removeListener
eventEmitter.on( 'removeListener', (event, listener) => {
    console.log(`The listener is removed from ${event}`);
});

// Declaring listener geek1 to myEvent1
var geek1  = (msg) => {
    console.log("Message from geek1: " + msg);
};

// Declaring listener geek2 to myEvent2
var geek2 = (msg) => {
    console.log("Message from geek2: " + msg);
};

// Listening to myEvent with geek1 and geek2
eventEmitter.on('myEvent', geek1);
eventEmitter.on('myEvent', geek2);

// Removing listener
eventEmitter.off('myEvent', geek1);

// Triggering myEvent
eventEmitter.emit('myEvent', 'Event occurred');

// Triggering error
eventEmitter.emit('error', new Error('Attention!'));
```

**输出:**

```
The listener is added to removeListener
The listener is added to myEvent
The listener is added to myEvent
The listener is removed from myEvent
Message from geek2: Event occurred
Attention! There was an error

```

**参考:**[https://nodejs . org/API/events . html # events _ class _ event emitter](https://nodejs.org/api/events.html#events_class_eventemitter)