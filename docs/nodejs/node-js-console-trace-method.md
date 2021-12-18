# Node.js console.trace()方法

> 原文:[https://www.geeksforgeeks.org/node-js-console-trace-method/](https://www.geeksforgeeks.org/node-js-console-trace-method/)

**console.trace()方法**是控制台模块的内置应用编程接口，用于将堆栈跟踪消息以换行符的形式打印到 stderr。类似于 console.error()方法。

**语法:**

```js
console.trace(message, args);
```

**参数:**该方法有两个参数，如上所述，描述如下:

1.  **消息:**此参数指定要打印的消息。
2.  **参数:**它是一个可选参数，指定要在消息中作为替换值传递的参数。所有传递的参数都被发送到 util.format()。

**返回值:**这个方法不返回任何东西，只打印“Trace:”字符串，后跟一个换行符中的格式化消息到 stderr，并堆栈跟踪到代码中的当前位置。

下面的例子说明了 **console.trace()方法**在 Node.js 中的使用:

**示例 1:**
**文件名:app.js**

```js
// Node.js program to demonstrate the 
// console.trace() method

// Accessing console module
const console = require('console');

// Calling console.trace() method
console.trace("stack teace sample");

console.trace(
    "stack trace sample with args: %d", 39);
```

使用以下命令运行 app.js 文件:

```js
node app.js
```

**输出:**

> 痕迹:在物体上叠加教学样本
> 。(C:\ nodejs \ g \ console \ console _ trace . js:4:9)
> at Module。_ 编译(内部/模块/cjs/loader.js:776:30)
> 在对象.模块. _ 扩展..js(internal/modules/cjs/loader . js:787:10)
> at module . load(internal/modules/cjs/loader . js:653:32)
> at tryModuleLoad(internal/modules/cjs/loader . js:593:12)
> at Function . module . _ load(internal/modules/cjs/loader . js:585:3)
> at Function。Module.runMain(内部/modules/cjs/loader.js:829:12)【启动时的 T7】(内部/引导/node . js:283:19)【bootstrapNodeJSCore 处的 T8】(内部/引导/node.js:622:3)
> Trace:对象处的带有 args: 39 的堆栈跟踪样本
> 。(C:\ nodejs \ g \ console \ console _ trace . js:5:9)
> at Module。_ 编译(内部/模块/cjs/loader.js:776:30)
> 在 Object.Module._extensions..js(internal/modules/cjs/loader . js:787:10)
> at module . load(internal/modules/cjs/loader . js:653:32)
> at tryModuleLoad(internal/modules/cjs/loader . js:593:12)
> at Function . module . _ load(internal/modules/cjs/loader . js:585:3)
> at Function。Module.runMain(内部/modules/cjs/loader.js:829:12)【启动时的 T17】(内部/引导/node.js:283:19)【启动时的 T18】(内部/引导/node.js:622:3)

**示例 2:**
**文件名:app.js**

```js
// Node.js program to demonstrate the 
// console.trace() method

// Accessing console module
const console = require('console');

// Calling console.trace() method
console.trace("stack trace message: "
    + "at %s: line no: %d ", "ff()", 96);

var isTrace = true;

console.custom_trace = function(message) {   
  if (isTrace) {
    console.trace(message);
  }
}

console.custom_trace("custom trace message");
```

使用以下命令运行 app.js 文件:

```js
node app.js
```

**输出:**

> 跟踪:堆栈跟踪消息:在 ff():行号:96
> 在对象。(C:\ nodejs \ g \ console \ console _ trace _ 1 . js:4:9)
> at Module。_ 编译(内部/模块/cjs/loader.js:776:30)
> 在对象.模块. _ 扩展..js(internal/modules/cjs/loader . js:787:10)
> at module . load(internal/modules/cjs/loader . js:653:32)
> at tryModuleLoad(internal/modules/cjs/loader . js:593:12)
> at Function . module . _ load(internal/modules/cjs/loader . js:585:3)
> at Function。Module.runMain(内部/modules/cjs/loader . js:829:12)
> 启动时(内部/引导/node.js:283:19)
> 在 bootstrapNodeJSCore(内部/引导/node.js:622:3)
> 跟踪:在 console . console . custom _ Trace(C:\ nodejs \ g \ console _ Trace _ 1 . js:11:13)
> 在(C:\ nodejs \ g \ console \ console _ trace _ 1 . js:14:9)
> at Module。_ 编译(内部/模块/cjs/loader . js:776:30)
> at object . module . _ extensions..js(internal/modules/cjs/loader . js:787:10)
> at module . load(internal/modules/cjs/loader . js:653:32)
> at tryModuleLoad(internal/modules/cjs/loader . js:593:12)
> at Function . module . _ load(internal/modules/cjs/loader . js:585:3)
> at Function。Module.runMain(内部/modules/cjs/loader.js:829:12)【启动时的 T18】(内部/引导/node.js:283:19)【启动时的 T19】(内部/引导/node.js:622:3)

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/console . html # console _ console _ trace _ data _ args](https://nodejs.org/api/console.html#console_console_trace_data_args)