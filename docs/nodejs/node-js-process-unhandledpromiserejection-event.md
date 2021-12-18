# Node.js 进程未处理承诺喷射事件

> 原文:[https://www . geesforgeks . org/node-js-process-unhandledprozerejection-event/](https://www.geeksforgeeks.org/node-js-process-unhandledpromiserejection-event/)

进程**是 Node.js 中的全局对象，它跟踪并包含在机器上特定时间执行的特定 node.js 进程的所有信息。**

**每当承诺拒绝未被处理时，就会发出*unhandled 落款* 事件。NodeJS 向控制台发出关于*未处理的错误警告*的警告，并立即终止进程。NodeJS 进程全局有一个 *unhandledRejection* 事件。当*未处理注射*发生且承诺链中没有处理者处理时，该事件被触发。**

****语法:****

```js
process.on("unhandledRejection", callbackfunction)
```

****参数:**该方法取以下两个参数。**

*   ****unhandled rejection:** is the name of the event emitted in the process.**
*   **[T0】 callback function: 【T1] is the event handler for the event.**

****返回类型:**该方法的返回类型为空。**

****示例 1:** 注册一个 *unhandledRejection* 侦听器的基本示例。**

## **index . js**

```js
// The unhandledRejection listener
process.on('unhandledRejection', error => {
    console.error('unhandledRejection', error);
});

// Reject a promise
Promise.reject('Invalid password');
```

**使用以下命令运行 **index.js** 文件:**

```js
node index.js
```

****输出:****

```js
unhandledRejection Invalid password
```

****示例 2:** 为了演示***unhandled rejection*侦听器只会在您的链中没有承诺拒绝处理程序时执行。****

## ****index . js****

```js
**// The unhandledRejection listener
process.on('unhandledRejection', error => {
    // Won't execute
    console.error('unhandledRejection', error);
});

// Reject a promise
Promise.reject('Invalid password')
    .catch(err => console.error(err))**
```

****使用以下命令运行 **index.js** 文件:****

```js
**node index.js**
```

******输出:******

```js
**Invalid password**
```

******<u>注意:</u>** 如果您使用监听器或消费者功能处理*取消处理投影*，那么控制台的默认警告(上述示例中的*取消处理投影警告*)将不会打印到控制台。****

******参考:**[https://nodejs . org/API/process . html # process _ event _ unhandledreprojection](https://nodejs.org/api/process.html#process_event_unhandledrejection)****