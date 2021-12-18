# 节点事件

> 原文:[https://www.geeksforgeeks.org/node-js-events/](https://www.geeksforgeeks.org/node-js-events/)

根据 Node.js 的官方文档，它是一个异步事件驱动的 JavaScript 运行时。Node.js 有一个**事件驱动架构**，可以执行异步任务。Node.js 具有**“事件”**模块，该模块发出命名事件，这些事件可以导致调用相应的函数或回调。函数(回调)侦听或订阅要发生的特定事件，当该事件触发时，订阅该事件的所有回调将按照它们被注册的顺序逐个触发。

**event emmitter 类:**所有发出事件的对象都是 EventEmitter 类的实例。在事件发射器的帮助下，可以发出事件或收听事件。

**语法:**

```js
const EventEmitter=require('events');
var eventEmitter=new EventEmitter();

```

**监听事件:**在发出任何事件之前，它必须注册函数(回调)来监听事件。
**语法:**

```js
eventEmitter.addListener(event, listener)
eventEmitter.on(event, listener)
eventEmitter.once(event, listener)

```

**eventEmmitter.on(事件，监听器)**和 **eventEmitter.addListener(事件，监听器)**非常相似。它在指定事件的侦听器数组末尾添加侦听器。对同一个事件和侦听器的多次调用将多次添加侦听器，并相应地激发多次。这两个函数都返回发射器，所以调用可以被链接。

**eventEmitter.once(event，listener)** 对于特定事件最多激发一次，在监听一次后将从 listeners 数组中移除。返回发射器，所以调用可以被链接。

**发射事件:**每个事件在 nodejs 中都被命名为事件。我们可以通过 emit(event，[arg1]，[arg2]，[…])函数触发一个事件。我们可以向侦听器函数传递任意一组参数。

**语法:**

```js
eventEmitter.emit(event, [arg1], [arg2], [...])

```

**简单事件:**

```js
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

```js
First event

```

**移除侦听器:****事件发射器.移除侦听器()**获取两个参数事件和侦听器，并从订阅该事件的侦听器数组中移除该侦听器。而**event emitter . removeall listeners()**从数组中移除订阅了所述事件的所有侦听器。

**语法:**

```js
eventEmitter.removeListener(event, listener)
eventEmitter.removeAllListeners([event])

```

**注:**

*   从数组中移除侦听器会改变侦听器数组的顺序，因此必须小心使用。
*   **event emitter . remove listener()**将删除队列前面最多一个侦听器实例。

```js
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter = new EventEmitter();

var fun1 = (msg) => {
    console.log("Message from fun1: " + msg);
};

var fun2 = (msg) => {
    console.log("Message from fun2: " + msg);
};

// Registering fun1 and fun2
eventEmitter.on('myEvent', fun1);
eventEmitter.on('myEvent', fun1);
eventEmitter.on('myEvent', fun2);

// Removing listener fun1 that was
// registered on the line 13
eventEmitter.removeListener('myEvent', fun1);

// Triggering myEvent
eventEmitter.emit('myEvent', "Event occurred");

// Removing all the listeners to myEvent
eventEmitter.removeAllListeners('myEvent');

// Triggering myEvent
eventEmitter.emit('myEvent', "Event occurred");
```

**输出:**

```js
Message from fun1: Event occurred
Message from fun2: Event occurred

```

我们注册了两次 fun1 和一次 fun2 来调用 event emitter . removelistener(' myEvent '，fun 1)fun 1 的一个实例将被移除。最后，通过 removeAllListeners()移除所有侦听器将移除 myEvent 的所有侦听器。

**其他方法:**默认情况下，任何单个事件最多可以注册 10 个监听器。要更改所有事件发射器实例的默认值，可以使用**事件发射器.默认最大侦听器**属性。**事件发射器. getMaxListeners()** 将返回 setMaxListeners()设置的最大侦听器值或默认值 10。

**注:**这不是硬性限制。事件发射器将允许添加新实例，但会打印一条警告消息，指示可能的事件发射器内存泄漏。

**语法:**

```js
eventEmitter.setMaxListeners(n)
eventEmitter.getMaxListeners()

```

```js
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter1 = new EventEmitter();
var eventEmitter2 = new EventEmitter();

// Getting max listener
console.log("Default max listener for eventEmitter1 is: ",
               eventEmitter1.getMaxListeners());
console.log("Default max listener for eventEmitter2 is: ",
              eventEmitter2.getMaxListeners());

// Set global deaultMaxListeners to 2
EventEmitter.defaultMaxListeners = 2;

// Getting max listener
console.log("Default max listener for eventEmitter1 is: ",
               eventEmitter1.getMaxListeners());
console.log("Default max listener for eventEmitter2 is: ",
               eventEmitter2.getMaxListeners());

// Set max listener of eventEmitter1 to 5
eventEmitter1.setMaxListeners(5);

// Getting max listener
console.log("Default max listener for eventEmitter1 is: ",
               eventEmitter1.getMaxListeners());
console.log("Default max listener for eventEmitter2 is: ",
               eventEmitter2.getMaxListeners());

// Declaring listener fun1 to myEvent1
var fun1 = (msg) => {
    console.log("Message from fun1: " + msg);
};

// Declaring listener fun2 to myEvent2
var fun2 = (msg) => {
    console.log("Message from fun2: " + msg);
};

// Listening to myEvent1 with 3 instance of fun1
for(var i = 0; i < 3; i++) {
    eventEmitter1.addListener('myEvent1', fun1)
}

// Listening to myEvent2 with 3 instance of fun2
for(var i = 0; i < 3; i++){
    eventEmitter2.addListener('myEvent2', fun2)
}

// Emitting myEvent1 and myEvent2
eventEmitter1.emit('myEvent1', 'Event1 occurred');
eventEmitter2.emit('myEvent2', 'Event2 occurred');
```

**输出:**

```js
Default max listener for eventEmitter1 is:  10
Default max listener for eventEmitter2 is:  10
Default max listener for eventEmitter1 is:  2
Default max listener for eventEmitter2 is:  2
Default max listener for eventEmitter1 is:  5
Default max listener for eventEmitter2 is:  2
Message from fun1: Event1 occurred
Message from fun1: Event1 occurred
Message from fun1: Event1 occurred
Message from fun2: Event2 occurred
Message from fun2: Event2 occurred
Message from fun2: Event2 occurred
(node:16240) MaxListenersExceededWarning: Possible EventEmitter memory leak detected.
3 myEvent2 listeners added. Use emitter.setMaxListeners() to increase limit

```

**event emitter . listeners():**它返回指定事件的侦听器数组。
**语法:**

```js
eventEmitter.listeners(event)
```

**event emitter . listener count():**返回监听指定事件的监听者数量。
**语法:**

```js
eventEmitter.listenerCount(event)
```

**event emitter . prependencelistener():**它会将一次性侦听器添加到数组的开头。
**语法:**

```js
eventEmitter.prependOnceListener(event, listener)
```

**event emitter . prepend listener():**它会将侦听器添加到数组的开头。
**语法:**

```js
eventEmitter.prependListener(event, listener)
```

```js
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter = new EventEmitter();

// Declaring listener fun1 to myEvent1
var fun1 = (msg) => {
    console.log("Message from fun1: " + msg);
};

// Declaring listener fun2 to myEvent2
var fun2 = (msg) => {
    console.log("Message from fun2: " + msg);
};

// Listening to myEvent with fun1 and fun2
eventEmitter.addListener('myEvent', fun1);

// fun2 will be inserted in front of listeners array
eventEmitter.prependListener('myEvent', fun2);

// Listing listeners
console.log(eventEmitter.listeners('myEvent'));

// Count the listeners registered to myEvent
console.log(eventEmitter.listenerCount('myEvent'));

// Triggering myEvent
eventEmitter.emit('myEvent', 'Event occurred');
```

**输出:**

```js
[ [Function: fun2], [Function: fun1] ]
2
Message from fun2: Event occurred
Message from fun1: Event occurred

```

**特殊事件:**当添加新的监听器和移除**【移除监听器】**现有监听器时，所有事件发射器实例都会发出事件**【新监听器】**。

*   **事件:“newListener”**事件发射器实例将在侦听器添加到其内部侦听器数组之前发出自己的“newListener”事件。为“newListener”事件注册的侦听器将被传递给正在添加的侦听器的事件名称和引用。在将侦听器添加到数组之前，会触发事件“newListener”。

    ```js
    eventEmitter.once( 'newListener', listener)
    eventEmitter.on( 'newListener', listener)
    ```

*   **事件:“移除监听器”****“移除监听器”**事件在监听器被移除后发出。

    ```js
    eventEmitter.once( ‘removeListener’, listener)
    eventEmitter.on( 'removeListener’, listener)
    ```

*   **事件:“错误”**当事件发射器实例中发生错误时，典型的操作是发出**“错误”**事件。如果事件发射器没有为“错误”事件注册至少一个侦听器，并且发出了“错误”事件，则会引发错误，打印堆栈跟踪，并退出 Node.js 进程。

    ```js
    eventEmitter.on('error', listener)

    ```

```js
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter = new EventEmitter();

// Register to error
eventEmitter.on('error', (err) => {
    console.error('whoops! there was an error');
});

// Register to newListener
eventEmitter.on( 'newListener', (event, listener) => {
    console.log(`The listener is added to ${event}`);
});

// Register to removeListener
eventEmitter.on( 'removeListener', (event, listener) => {
    console.log(`The listener is removed from ${event}`);
});

// Declaring listener fun1 to myEvent1
var fun1 = (msg) => {
    console.log("Message from fun1: " + msg);
};

// Declaring listener fun2 to myEvent2
var fun2 = (msg) => {
    console.log("Message from fun2: " + msg);
};

// Listening to myEvent with fun1 and fun2
eventEmitter.on('myEvent', fun1);
eventEmitter.on('myEvent', fun2);

// Removing listener
eventEmitter.off('myEvent', fun1);

// Triggering myEvent
eventEmitter.emit('myEvent', 'Event occurred');

// Triggering error
eventEmitter.emit('error', new Error('whoops!'));
```

**输出:**

```js
The listener is added to removeListener
The listener is added to myEvent
The listener is added to myEvent
The listener is removed from myEvent
Message from fun2: Event occurred
whoops! there was an error

```

**异步事件:**event emitter 按照注册的顺序同步调用所有侦听器。但是，我们可以通过使用 **setImmediate()或 process.nextTick()** 来执行异步调用。

```js
// Importing events
const EventEmitter = require('events');

// Initializing event emitter instances 
var eventEmitter = new EventEmitter();

// Async function listening to myEvent
eventEmitter.on('myEvent', (msg) => {
    setImmediate( () => {
        console.log("Message from async: " + msg);
    });
});

// Declaring listener fun to myEvent
var fun = (msg) => {
    console.log("Message from fun: " + msg);
};

// Listening to myEvent with fun
eventEmitter.on('myEvent', fun);

// Triggering myEvent
eventEmitter.emit('myEvent', "Event occurred");
```

**输出:**

```js
Message from fun: Event occurred
Message from async: Event occurred

```

**参考:**T2】https://nodejs.org/api/events.html