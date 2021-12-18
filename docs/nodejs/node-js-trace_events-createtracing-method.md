# node . js trace _ events . createtracing()方法

> 原文:[https://www . geesforgeks . org/node-js-trace _ events-create tracing-method/](https://www.geeksforgeeks.org/node-js-trace_events-createtracing-method/)

**trace_events.createTracing(选项)** ( *在 v10.0.0* 中添加)方法是“trace_events”模块的内置应用程序编程接口，该接口创建 Tracing 对象，并为给定的类别集返回相同的内容。trace_events 模块包含用于启用或禁用类别集跟踪的跟踪对象。

**语法:**

```
trace_events.createTracing(options)
```

为了使用这个(*trace _ events . createtracing()*)方法，我们需要导入‘trace _ events’模块。

```
const trace_events = require('trace_events');  

```

**参数:**该函数接受对象作为参数，如上所述，如下所述:

*   **选项** < *对象* > **:** 它接受一个对象，该对象包含一些跟踪时需要的分类字符串值。

*   **类别** < *字符串[]* >它接受包含跟踪类别名称的字符串数组。如果可能的话，将这些值包含在数组中，并将其转换为字符串。如果无法说服该值，将返回一个错误。

**返回值** < *追踪* > **:** 返回包含类别< *字符串[]* >和启用的< *布尔* >值的对象。

下面的程序说明了 Node.js 中的*trace _ events . createtracing()*方法:

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// trace_events.createTracing() methods 

// Using require to access trace_events module 
const tracing_events = require("trace_events");

// Different types of tracing categories
const categories = [ 'myapp.category', 
    'v8', 'node', 'node.async_hooks', 
    'node.promises.rejections', 
    'node.vm.script', 'node.perf.usertiming', 
    'node.perf.timerify'
];

// Now creating tracing for custom
// trace category.
const newTracing = tracing_events.createTracing(
    { categories });

// Printing tracing event
console.log(newTracing);
```

**输出:**

> >>跟踪{
> 已启用:false，
> 类别:' myapp.category，v8，node，node.async_hooks，
> node . promises . rejects，node.vm.script，node.perf.usertiming，node.perf.timerify'
> }

**示例 2:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// trace_events.createTracing() methods 

// Using require to access trace_events module 
const { createTracing } = require('trace_events');

// Now create tracing for custom trace category.
const tracing = createTracing({ categories: ['perf_hooks', 
'node.promises.rejections'] });
console.log("Tracing Created...");

// Printing tracing event
console.log(tracing);

// Enabling Tracing event
tracing.enable();

// Do some steff here
const perf_hooks = require("perf_hooks");
perf_hooks.performance.mark("A");
() => {
  perf_hooks.performance.mark("B");
  perf_hooks.performance.measure("A to B", "C", "D");
};

// Disabling tracing event
tracing.disable();
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

**输出:**

> 已创建跟踪…
> 
> 跟踪{已启用:false，类别:' perf_hooks，node . promises . rejects ' }

**参考:**[https://nodejs . org/API/tracing . html # tracing _ trace _ events _ createtracing _ options](https://nodejs.org/api/tracing.html#tracing_trace_events_createtracing_options)