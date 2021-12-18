# Node.js 追踪对象

> 原文:[https://www.geeksforgeeks.org/node-js-tracing-objects/](https://www.geeksforgeeks.org/node-js-tracing-objects/)

**追踪对象** ( *在 v10.0.0* 中添加)用于一组类别，以启用和禁用追踪。创建跟踪事件后，通过调用 tracing.enable()方法禁用跟踪对象，然后将类别添加到启用的跟踪集中，并可通过调用 **tracing.categories** 进行访问。

**下面提到一些追踪对象:**

1.  **tracing . categories****(*在 v10.0.0* 中添加) **:** 对象是“trace_events”模块的内置应用程序编程接口，该接口返回 trace 事件类别，该类别是该 Tracing 对象所覆盖的逗号分隔列表。**

    ****语法:****

    ```
    tracing.categories
    ```

    ****参数:**该对象不接受上述任何参数。**

     ****返回值** < *字符串* > **:** 返回以逗号分隔的跟踪事件类别列表。** 
2.  ****【tracing . disable()】****(*在 v10.0.0* 中增加) **:** 对象是‘trace _ events’模块的内置应用编程接口，用于禁用之前通过 *tracing.enable()* 方法启用的 Tracing 对象。****

    ******语法:******

    ```
    **tracing.disable()**
    ```

    ******参数:**该对象不接受任何参数。****

    ******返回值:**不返回值，而是禁用跟踪事件。****

3.  ******【tracing.enable()】**(*在 v10.0.0 中添加)* **:** 对象是“trace_events”模块的内置应用程序编程接口，该接口为之前通过 tracing . enable()方法启用的类别集启用 Tracing 对象。****

    ******语法:******

    ```
    **tracing.enable()**
    ```

    ******参数:**该对象不接受任何参数。****

     ******返回值:**不返回值，而是启用跟踪事件。**** 
4.  ******tracing . enabled****(*在 v10.0.0* 中添加) **:** 此对象跟踪 trace 事件是启用还是禁用，并相应地返回布尔值。******

    ******语法:******

    ```
    **tracing.enabled**
    ```

    ******参数:**该对象不接受任何参数。****

    ******返回值** < *布尔* > **:** 仅当追踪对象已启用时才返回真。****

****下面的程序说明了 Node.js 中的跟踪对象:****

******安装 trace_events 模块:******

```
**npm install trace_events**
```

******示例 1:** **文件名:index.js******

```
**// Node.js program to demonstrate the 
// Tracing methods 

// Using require to access trace_events module 
const trace_events = require('trace_events'); 

const newTraceEvent1 = trace_events.createTracing({ 
categories: ['node.perf.usertiming', 'v8'] });

const { createTracing } = require('trace_events');

const newTraceEvent2 = createTracing({ 
categories: ['node', 'node.promises.rejections'] });

newTraceEvent1.enable();
newTraceEvent2.enable();

// Prints newTraceEvent1 trace event
console.log(newTraceEvent1);

// Prints newTraceEvent2 trace event
console.log(newTraceEvent2);

// Prints all enabled categories
console.log(trace_events.getEnabledCategories());

// Disable 'node, node.promises.rejections' category
newTraceEvent2.disable(); 

// Prints 'node.perf.usertiming, v8'
console.log(trace_events.getEnabledCategories());

// Disable 'node.perf.usertiming' category
newTraceEvent1.disable();**
```

****使用以下命令运行 **index.js** 文件:****

```
**node index.js**
```

******输出:******

> ****跟踪{已启用:true，类别:' ' node.perf.usertiming，v8' }
> 跟踪{已启用:true，类别:' ' node，node.promises.rejections' }
> 节点，node.perf.usertiming，node . promises . rejects，v8
> node.perf.usertiming，v8****

******示例 2:** **文件名:index.js******

```
**// Node.js program to demonstrate the 
// Trace methods 

// Using require to access trace_events module 
const trace_events = require("trace_events");

// Tracing categories
const categories = [ 'myapp.category', 'v8', 'node', 
'node.async_hooks', 'node.promises.rejections', 'node.vm.script', 
'node.perf.usertiming', 'node.perf.timerify'];

// Now create tracing for custom trace category.
const newTracing = trace_events.createTracing({ categories });

// Printing tracing event
console.log(newTracing);

// Printing tracing categories
console.log(newTracing.categories);

// Checking wheather trace is enabled or not
console.log(newTracing.enabled);

// Enabling newTracing
newTracing.enable();

// Printing tracing categories
console.log(newTracing.categories);

// Checking wheather trace is enabled or not
console.log(newTracing.enabled);

// Do some stuff
const perf_hooks = require("perf_hooks");
perf_hooks.performance.mark("Alfa");
() => {
  perf_hooks.performance.mark("Beta");
  perf_hooks.performance.measure(
      "Alfa to Beta", "Alfa", "Beta");
};

// Prints performance stuff
console.log(perf_hooks.performance);

// Disables newTracing
newTracing.disable();**
```

****使用以下命令运行 **index.js** 文件:****

```
**node index.js
**For custom tracing**
node --trace-event-categories v8, node, node.async_hooks index.js** 
```

******输出:******

> ****> >跟踪{已启用:false，类别:' ' myapp.category，…。，node . perf . time rify ' }
> >>myapp . category，v8，…..，node . perf . time rify
> >>false
> >>my app . category，v8，…，node . perf . time rify
> >>true
> >>{ node timing:{ name:' node '，…loopExit: -1 }，
> time origin:1596967720328.603 }****

*****浏览器中的追踪*:在谷歌 Chrome 中输入 URL[*Chrome://追踪*](//tracing) 。现在，单击加载按钮，加载文件进行跟踪。****

******参考:**T2】https://nodejs.org/api/tracing.html#tracing_tracing_object****