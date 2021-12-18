# Node.js 过程警告事件

> 原文:[https://www . geesforgeks . org/node-js-process-warning-event/](https://www.geeksforgeeks.org/node-js-process-warning-event/)

**“警告”**是流程模块中流程类的事件，每当 Node.js 发出流程警告时就会发出。

**语法:**

```js
Event: 'warning'
```

**参数:**此事件不接受任何参数作为参数。

**返回值:**此事件只返回一个回调函数，以便进一步操作。

**例 1:**

## index.js

```js
// Node.js program to demonstrate the  
// Process 'warning' Event

// Importing process module
const process = require('process');

// Intentionally emitted warning
process.emitWarning('something strange happened');

// Event 'warning' 
process.on('warning', (warning) => {
   console.warn("warning name - " + warning.name);
   console.warn("warning message - " + warning.message);
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
(node:8004) Warning: something strange happened
(Use `node --trace-warnings ...` to show where
the warning was created)
warning name - Warning
warning message - something strange happened
```

**例 2:**

## index.js

```js
// Node.js program to demonstrate the  
// Process 'warning' Event

// Importing process module
const process = require('process');

// Intentionally emitted warning
process.emitWarning('Running out of Storage');

// Event 'warning' 
process.on('warning', (warning) => {
  console.warn("warning stacktrace - " + warning.stack)
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> (节点:13400)警告:存储空间不足
> (使用“节点-跟踪-警告...”来显示创建警告的位置)
> 警告堆栈跟踪-警告:对象上的存储空间不足
> 。<匿名>(F:\ Java \ gfg . js:8:9)
> at Module。_ 编译(节点:内部/模块/cjs/加载器:1109:14)
> 在对象.模块. _ 扩展..js(节点:内部/模块/cjs/加载器:1138:10)
> at Module.load(节点:内部/模块/cjs/加载器:989:32)
> at function . module . _ load(节点:内部/模块/cjs/加载器:829:14)
> at function . executeuserentrypoint[as runMain](节点:内部/模块/run_main:76:12)
> at 节点:内部/main/run_main_module

**参考**:[https://nodejs . org/dist/latest-v 16 . x/docs/API/process . html # process _ event _ warning](https://nodejs.org/dist/latest-v16.x/docs/api/process.html#process_event_warning)