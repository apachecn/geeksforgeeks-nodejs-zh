# node . js util . debugog()方法

> 原文:[https://www.geeksforgeeks.org/node-js-util-debuglog-method/](https://www.geeksforgeeks.org/node-js-util-debuglog-method/)

“ *util* ”模块提供了用于调试目的的“*实用程序*”功能。为了访问这些函数，我们需要调用它们(通过'*require(' util '*')。

**util.debuglog()** (在 v0.11.3 中添加)方法是 util 模块的内置应用程序编程接口，用于创建基于 *NODE_DEBUG* 环境变量的函数，该环境变量将调试消息有条件地写入 *stderr* 。如果部分名称出现在该环境变量的值中，则返回的函数以与 *console.error()* 相同的方式运行。如果不是，则返回的函数是*无操作*。

**语法:**

```js
util.debuglog(section[, callback])
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **部分** < *字符串* >:它接受一个< *字符串* >，标识正在为其创建 debuglog 函数的应用程序部分。
*   **回调** < *函数* >:接受第一次调用日志记录函数时调用的回调，函数参数为更优化的日志记录函数..

**返回值** < *功能* >:返回测井功能。

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the 
// util.debuglog() method 

// Using require to access util module 
const util = require('util');

const debugLog = util.debuglog('run-app');

// Use debuglog() method
debugLog('hello from my debugger [%d]', 123);
// SET NODE_DEBUG=run-app&&node util.js

// Another way to import debuglog
const { debuglog } = require('util');

const debuglogue = debuglog('run-app1');

// Use debuglog() method
debuglogue('hello from run-app [%d]', 123);

const a = "old Value";

let deebuglog = util.debuglog('run-app2',
    (debuging) => {

        // Replace with a logging function
        // that optimizes out
        a = "new Value";

        // Testing if the section is enabled
        deebuglog = debuging;
    });

// prints the debuglog function 
console.log(util.inspect(deebuglog, 
    showHidden = true, compact = true));

// Prints nothing
console.log(a);

// logs app *
deebuglog();

deebuglog('hi there, it\'s run-app [%d]', 2333);
```

使用以下命令运行 **index.js** 文件:

```js
SET NODE_DEBUG=run-app*&&node index.js
***OR*** 
NODE_DEBUG=run-app* node index.js

```

**输出:**

> > > RUN-APP 8112:我的调试器您好[123]
> 
> > > RUN-APP1 8112:来自 run-app [123]的您好
> 
> > ><ref>【函数(匿名)】{……[原型]:{[构造函数]:[循环*1] }</ref>
> 
> }
> 
> >>旧值
> 
> >>运行-APP2 8112:
> 
> > > RUN-APP2 8112:嗨，这里是 run-app [2333]

**示例 2:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the 
// util.debuglog() method 

// Using require to access util module 
const util = require('util');
// const {debuglog} = require('util');

const debuglog = util.debuglog('alfa-beta');

debuglog('Hii there, debuglog from alfa-beta [%d]', 2333);

const generalLog = util.debuglog('alfa-');
const timerLog = util.debuglog('alfa-romeo');
const delay = 800;

generalLog('Leaving alfa-...');
console.log("Wait for timerLog...")
setTimeout(() => {
    timerLog('timer fired after %d ', delay);
}, delay);
```

使用以下命令运行 **index.js** 文件:

```js
SET NODE_DEBUG=alfa-*&&node index.js
***OR***
NODE_DEBUG=alfa-* node index.js

```

**输出:**

> 阿尔法-贝塔 7008:那里的 Hii，来自阿尔法-贝塔的 debug log[2333]
> 
> 阿尔法- 7008:离开阿尔法-…
> 
> 等待时间日志…
> 
> 阿尔法-罗密欧 7008:800 后计时器启动

**参考:**[https://nodejs . org/API/util . html # util _ util _ debug log _ section _ callback](https://nodejs.org/api/util.html#util_util_debuglog_section_callback)