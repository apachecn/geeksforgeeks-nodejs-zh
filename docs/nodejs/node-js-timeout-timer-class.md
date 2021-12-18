# Node.js 超时定时器类

> 原文:[https://www.geeksforgeeks.org/node-js-timeout-timer-class/](https://www.geeksforgeeks.org/node-js-timeout-timer-class/)

计时器模块用于调度将在未来某个时间段调用的功能。它是一个全局的应用编程接口，所以不需要导入(需要(“定时器”)来使用它。

超时类有一个对象(*setTimeout()/setInterval()*)是内部为预定操作创建的，可以传递(*cleartime out()/clearInterval()*)来取消那些预定操作。当计划超时时，默认情况下，Node.js 的事件循环将继续运行，直到调用 *clearTimeout()* 为止。 *setTimeout()* 方法返回用于控制此默认行为的超时对象，同时导出 *timeout.ref()* 和 *timeout.unref()* 函数。

**四个超时类对象定义如下:**

**1。timeout.hasRef():** (在 v11.0.0 中添加)此超时对象保持事件循环活动，直到返回的“真”打破事件循环。

**语法:**

timeout.hasRef()

**返回值** < *布尔* > **:** 如果返回“真”，该超时对象将保持事件循环活动。

**2。timeout.ref():** (在 v9.7.0 中添加)当 timeout 处于活动状态并且( *timeout.ref()* )被调用时，它会请求 Node.js 事件循环没有退出这么长时间。无论如何，多次调用此方法没有任何效果。

**语法:**

timeout.ref()

**返回值** < *超时* >:返回超时引用。

**3。timeout.refresh()** ( *在 v10.2.0 中添加)* **:** 该方法在不分配新的 JavaScript 对象的情况下刷新计时器。计时器的开始时间设置为当前时间，并通过调用其回调将计时器从先前指定的持续时间重新安排为当前时间。通过对已经调用其回调的计时器使用 timeout.refresh()，然后重新激活计时器。

**语法:**

超时.刷新()

**返回值** < *超时* > **:返回超时参考。**

**4。timeout.unref()** (在 v9.7.0 中添加)当 timeout 处于活动状态时，它不要求 Node.js 事件循环保持活动状态。如果任何其他活动保持事件循环运行，则在进程退出后调用超时对象的回调。反正多次调用这个方法也没有任何效果。

**语法:**

timeout.unref()

**返回值** < *超时* > **:返回超时参考。**

**示例:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// Timeout Class methods

// Setting Timeout by setTimeout Method
var Timeout = setTimeout(function alfa() {
    console.log("0.> Setting Timeout", 12);
});

// Printing Timeout.hasRef method
console.log("1 =>", Timeout.hasRef());
// returns true

// Printing Timeout.ref before unref
console.log("2 =>", Timeout.ref());
Timeout.unref()
Timeout.ref()
// Returns timer reference

// Printing Timeout.refresh before unref
console.log("3 =>", Timeout.refresh());
// Returns timer reference

// Printing Timeout.unref method
console.log("4 =>", Timeout.unref());
// Returns Timeout reference and sets
// hasRef to false

// Printing Timeout.hasRef before unref
console.log("5 =>", Timeout.hasRef());
// Returns false

// Clears setInterval Timeout
clearTimeout(Timeout);
// Prints after clearing Timeout

console.log("6 => Printing after clearing Timeout");
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 1 = >真
> 2 = >超时{
> _idleTimeout: 1，
> _idlePrev:【定时器列表】，
> _idleNext:【定时器列表】，
> _idleStart: 52，
> _onTimeout:【功能:alfa】，
> _timerArgs:未定义，
> _repeat: null，
> _ 销毁:假，
> 【符号(refed)】:真，
> 【符号(asyncId)】:2，【2
> 【符号(asyncId)】:2、
> 【符号(triggerId)】:1
> }
> 4 =>超时{
> _idleTimeout: 1、
> _ idle prev:【time rslist】、
> _ idle next:【time rslist】、
> _idleStart: 87、
> _onTimeout:【函数:alfa】、
> _timerArgs:未定义、
> _repeat: null

**参考:**T2】https://nodejs.org/api/timers.html#timers_class_timeout