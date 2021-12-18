# node . js trace _ events . getenabledcategories()方法

> 原文:[https://www . geesforgeks . org/node-js-trace _ events-getenabledcategories-method/](https://www.geeksforgeeks.org/node-js-trace_events-getenabledcategories-method/)

**trace_events . getenabledcategories()**(*在 v10.0.0* 中添加)方法是“trace _ events”模块的内置应用程序编程接口，用于显示由所有当前启用的跟踪对象的并集确定的当前启用的跟踪事件类别集。默认情况下，它的状态被 v8 运行时禁用，所有启用的类别都使用*-跟踪-事件-类别*标志提取。

**语法:**

```js
trace_events.getEnabledCategories()

```

为了使用这个方法，我们需要使用(*trace _ events . createtracing()*)方法创建跟踪事件，并且我们需要导入‘trace _ events’模块。

```js
const trace_events = require('trace_events');  

```

**参数:**此方法不接受任何参数。

**返回值** < *字符串* >:返回当前启用的所有跟踪事件类别列表，列表之间用逗号分隔。

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// trace_events.getEnabledCategories() method 

// Using require to access trace_events module 
const trace_events = require('trace_events');

// Creating trace events
const trace_event1 = trace_events
    .createTracing({ categories: ['node'] });
const trace_event2 = trace_events.createTracing({
    categories: ['node.promises.rejections']
});
const { createTracing } = require('trace_events');

// Another way to create Tracing events
const trace_event3 = createTracing(
        { categories: ['node.vm.script'] });

// Enabling the trace_event1
trace_event1.enable();

// Enabling the trace_event2
trace_event2.enable();

// Printing the enabled categories
console.log("Enabled categories: ", 
    trace_events.getEnabledCategories());

// Disabling the trace_event1 
trace_event1.disable();

// Disabling the trace_event2 
trace_event2.disable();
```

**输出:**

```js
Enabled categories node,node.promises.rejections

```

**示例 2:** **文件名:**

```js
// Node.js program to demonstrate the 
// trace_events.getEnabledCategories() method 

// Using require to access trace_events module 
const trace_events = require('trace_events');

// Tracing categories
const categories = ['myapp.category', 'v8', 'node', 
    'node.async_hooks', 'node.promises.rejections', 
    'node.vm.script', 'node.perf.usertiming',
    'node.perf.timerify'];

// Now create tracing for custom trace category.
const tracing = trace_events.createTracing({ categories });

// Enabling Tracing event
tracing.enable();

// Printing tracing event
console.log(">> ", tracing);

// Returns false if any tracing event is enabled 
console.log(">> ", !trace_events.getEnabledCategories());

if (trace_events.getEnabledCategories()) {
    console.log(">> Following tracing events are enabled",
        trace_events.getEnabledCategories());
} else {
    console.log(">> None of the Tracing events are enabled");
}

// Disabling tracing event
tracing.disable();

if (trace_events.getEnabledCategories()) {
    console.log(">> Following tracing events are enabled",
        trace_events.getEnabledCategories());
} else {
    console.log(">> None of the Tracing events are enabled");
}
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

> > >跟踪{启用:true，
> 
> 类别:【myapp.category，v8，node，node.async_hooks，node . promises . rejects，node.vm.script，node.perf.usertiming，node . perf . time rify】}
> 
> >>false
> 
> >>启用以下跟踪事件:myapp.category，node，node.async_hooks，node perf。

**参考:**[https://nodejs . org/API/tracing . html # tracing _ trace _ events _ getenabledcategories](https://nodejs.org/api/tracing.html#tracing_trace_events_getenabledcategories)