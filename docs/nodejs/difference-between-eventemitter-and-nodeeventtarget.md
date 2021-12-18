# 事件发射器和节点事件目标之间的差异

> 原文:[https://www . geesforgeks . org/difference-event emitter-and-nodeventtarget/](https://www.geeksforgeeks.org/difference-between-eventemitter-and-nodeeventtarget/)

**事件发射器:**所有*事件发射器*在添加新侦听器时发出事件“*新侦听器*”，在移除现有侦听器时发出事件“*移除侦听器*”。它由事件模块定义和公开:

要导入*事件发射器*，请使用以下导入语句:

```
const EventEmitter = require('events');
```

**节点事件目标:***事件目标*和事件对象是*事件目标*网络应用编程接口的特定于节点. js 的实现，由一些*节点. js* 核心应用编程接口公开。

**区别***T5【事件发射器】*T8*T11【节点事件目标】***:**

| Event transmitter | Node event target |
| --- | --- |
| It is inherited from the *event* module of JavaScript. | Is a modified subset of the *event emitter* API and inherits from this API. |
| It realizes the relationship between *IS-A* and *Event* modules. | It realizes the IS-A relationship between *and *event target* API.* |
| In *Event Emitter* , we can register multiple listeners for the same event. | Each event type can register any listener once. If you try to register a listener several times, it will be ignored. |
| It imitates most from events such as *, [error], [class], [emission] and* . | 它没有模仿完整的*事件发射器* API，如*前置监听者()*、*前置监听者()*、*监听者()*等。 |
| The default behavior is to record *with* information and end the current execution. | For events of type " *error* ", it does not implement any default behavior. |
| If an error occurs in the *event transmitter* instance, the typical operation is to issue an "error" event. | The *event listener* object is supported as a handler for all event types. |
| All event emitters emit the event " *new listener* " when adding a new listener, and the event "removeListener" when removing the listener. | It is not an instance of the *event transmitter* , and in most cases, it cannot be used instead of the event transmitter. |
| **语法:**

```
emitter.once(
  eventName, listener)
```

 | **语法:**

```
nodeEventTarget.once(
  type, listener[, options])
```

 |

**参考:**[https://nodejs . org/API/events . html # events _ nodeventtarget _ vs _ event emitter](https://nodejs.org/api/events.html#events_nodeeventtarget_vs_eventemitter)