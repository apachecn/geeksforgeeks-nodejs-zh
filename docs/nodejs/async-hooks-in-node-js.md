# node . js 中的异步钩子

> 原文:[https://www.geeksforgeeks.org/async-hooks-in-node-js/](https://www.geeksforgeeks.org/async-hooks-in-node-js/)

**Async_hooks** 模块之所以被使用，是因为它提供了一个 API 来注册回调，跟踪 Node.js 应用程序内部创建的异步资源的生存期。

**特征:**

*   您可以捕获 Node.js 进程中的任何异步活动。
*   最小的性能开销。
*   强大灵活的 API。

这些资源在 C++中被跟踪，从 AsyncWrap 类继承的任何东西都是异步资源。

**异步资源的生命时间事件:**

1.  **init(asyncId，type，triggerAsyncId，resource):** 当构造一个有可能发出异步事件的类时调用。
    *   **异步标识:**异步资源的唯一标识。
    *   **类型:**异步资源的类型。
    *   **触发同步标识:**异步资源的唯一标识。
    *   **资源:**对代表异步操作的资源的引用，需要在销毁期间释放。
2.  **之前(asyncId)和之后(asyncId):**
    *   在执行注册用户回调之前调用之前。
    *   执行注册用户回调后立即调用后的**。**
3.  **销毁(asyncId):** 销毁 asyncId 对应的资源后调用。

```js
function destroy(id) {
    print({ stage: 'destroy', id })
}

const hook = asyncHooks.createHook(
    { init, before, after, destroy })
```

**输出:**

```js
{id:2, type:'Timeout', triggerAsyncId:3 }
{id:3, type:'TIMEWRAP', triggerAsyncId:3 }
{stage: 'before', id: 4}
{stage: 'before', id:2}
'User callback fired'
{stage: 'after', id: 2}
{stage: 'after', id:3}
{stage: 'destroy', id: 2}
{stage: 'destroy', id:3}

```

该应用编程接口允许从节点的内置本机模块(如 fs 和 net)中侦听低级异步资源。
**异步钩子高级应用编程接口**fs . stat、fs.read、fs.open、fs.close 由一个提供程序表示，然后以对用户更有意义的方式公开，然后组合成更高级的操作。基本上，如果我们在跟踪我们的进程，寻找 CPU 使用情况，内存使用情况，我们不会每秒拍摄堆快照，这将杀死我们的服务器。我们来了异步钩子，当服务器运行时，我们需要更少的细节，这使得操作更快，信息更多。
**注意:** Node.js 也想通过 async_hooks 公开未包装的内部定时器，但是目前，它们太贵了。CLS 用例也不需要这些，但是对于一些极端的用例，您可能想要观察所有的异步活动，甚至包括内部定时器。
人们可以想象 async_hooks 的一种模式，这种模式也可以观察到这些内部资源，而且它是选择加入的，因为这是有代价的。