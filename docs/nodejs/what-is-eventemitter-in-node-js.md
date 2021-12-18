# node . js 中的 EventEmitter 是什么？

> 原文:[https://www . geesforgeks . org/what-is-event emitter-in-node-js/](https://www.geeksforgeeks.org/what-is-eventemitter-in-node-js/)

EventEmitter 是 node.js 中的一个类，负责处理使用 node.js 中的“events”模块创建的事件。创建事件是为了在执行一组操作时进行自定义操作。如果我们想要创建一个新的事件监听器，EventEmitter 可以返回两个属性，即 *newListener* ，如果我们想要移除现有的事件监听器，则返回 *removeListener* 。无论何时调用这两个属性来执行操作，都会发出一个事件。

为了在事件发射器上执行操作，我们需要使用“事件”模块创建一个引用，然后我们需要初始化事件发射器的一个实例，以便我们可以进一步使用它。

**语法:**

```js
// Creating a constant reference of EventEmitter
const EventEmittter = require('events');

// Initializing instance of EventEmitter
var emitter = new EventEmitter();
```

**使用 addListener 创建监听事件:**在我们发出事件之前，我们必须创建一个监听发出的回调的监听程序，然后监听程序将继续执行遵守事件所需的进一步操作。我们可以借助事件发射器的*添加监听器*属性来创建一个事件监听器。 *addListener* 将事件追加到数组的末尾，这样我们就可以多次调用它来调用事件的多个实例，这非常有用，因为我们不需要多次编写事件。

**语法:**

```js
emitter.addListener(eventName, listener);
```

**发出事件:**由于 node.js 中的每个事件都是一个命名事件，所以我们可以通过使用 emit 方法来触发一个事件，并且我们可以传递任意参数来监听事件。

**语法:**

```js
emitter.emit(eventName, arg1,arg2,...)
```

**示例:**使用 addListener 方法创建事件发射器和添加事件的代码。

## Javascript

```js
// Importing the events module
const EventEmitter = require('events');

// Initializing instance of EventEmitter to be used
var emitter = new EventEmitter();

// Adding listener to the event
emitter.addListener('welcomeEvent', (name) => {
   console.log("welcome " + name);
});

// Emitting the welcomeEvent
emitter.emit('myEvent', "Geek");
```

**输出:**

```js
welcome Geek
```

**移除事件的一个实例:**如果我们想从事件中移除一个特定的侦听器，我们可以使用两种方法来移除事件*移除侦听器*或者如果我们想从事件中移除所有侦听器的一个实例，我们可以使用*移除所有侦听器*。

**语法:**

```js
// For removing any single listener form the event
emitter.removeListener(eventName, listener)

// For removing all listeners of the event
emitter.removeAllListeners(eventName)
```

**示例:**移除事件的事件侦听器的代码。

## Javascript

```js
// Importing the events module
const EventEmitter = require('events');

// Initializing instance of EventEmitter to be used
var emitter = new EventEmitter();

// Creating events 
var robot1 = (msg) => {
    console.log("Message from person1: " + msg);
};

var person2 = (msg) => {
    console.log("Message from person2: " + msg);
};

// Registering person1 and person2 with the printEvent
emitter.addListener('printEvent', person1);
emitter.addListener('printEvent', person2);

// Triggering the created event
emitter.emit('printEvent', "Event occurred");

// Removing all the listeners associated with the event
emitter.removeAllListeners('printEvent');

// Triggering the event again but no output
// as all listeners are removed
emitter.emit('printEvent', "Event occurred");
```

**输出:**

```js
Message from person1: Event occurred
Message from person2: Event occurred
```

正如您在上面的输出中看到的，事件被触发了两次，但是输出只出现了一次，因为我们删除了事件侦听器，所以在第二次发出事件时没有侦听器出现。