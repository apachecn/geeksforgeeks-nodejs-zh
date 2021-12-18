# 如何在 Node.js 中暂停特定时间？

> 原文:[https://www . geesforgeks . org/如何在特定时间在节点中暂停 js/](https://www.geeksforgeeks.org/how-to-pause-in-node-js-for-a-specific-time/)

有时，我们需要在一段时间后执行一些功能，就像您向用户要求的那样，服务器端的下一个功能需要详细信息。那一次我们需要暂停服务器。所以要暂停特定时间，我们使用 [setTimeout()功能](https://www.geeksforgeeks.org/node-js-http-server-settimeout-method/)。它有一个附加的回调函数，在给定的时间后执行。 **setTimeout()** 可用于在给定的毫秒数后执行代码。

对于多个函数，您可以做的一件事是，您可以将函数分成不同的代码块，并在它们之间使用 setTimeout()。

**语法:**

```js
setTimeout(function, milliseconds);
```

下面的例子说明了使用 setTimeout()函数暂停节点的方法:

**示例:**该功能在引擎盖下使用 **setTimeout()** 显示极客！2 秒后**你好**。这里的文件名是 wait.js。

## 等等. js

```js
function sleep(ms) {
  return new Promise((resolve) => setTimeout(resolve, ms));
}

console.log("Hello");
sleep(2000).then(() => {
  console.log("Geek!");
});
```

**输出:**

![](img/6ba07867cfcb76ffc04c67ce4a00e2e5.png)