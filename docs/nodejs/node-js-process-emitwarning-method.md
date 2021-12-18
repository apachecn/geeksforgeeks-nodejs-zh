# Node.js process.emitWarning()方法

> 原文:[https://www . geesforgeks . org/node-js-process-emit warning-method/](https://www.geeksforgeeks.org/node-js-process-emitwarning-method/)

**process.emitWarning()** 方法是流程模块的内置应用程序编程接口，用于发送自定义或特定于应用程序的流程警告。

**语法:**

```js
process.emitWarning(warning[, options])
```

**参数:**该函数接受以下参数:

*   **警告:**用于表示将要发出的警告。
*   **选项:**是可选参数，可以有以下属性:
    *   **类型:**用于表示警告为字符串形式时发出的警告类型。
    *   **代码:**用于表示发出的警告实例的唯一标识符。
    *   **ctor:** 这是一个可选函数，用于在警告为字符串形式时限制生成的堆栈跟踪。
    *   **详细信息:**用于添加要包含在错误中的附加文本。

**返回值:**此事件只返回一个回调函数，以便进一步操作。

**示例 1:****process . emit warning()**方法在监听进程的同时将错误对象传递给警告处理程序。

## index.js

```js
console.log("Start ...");

// Use setInterval to keep the process running
setInterval(() => {
    console.log("Working ...");
}, 1000);

setTimeout(() => {
    process.emitWarning('Something happened!', {
        code: 'Custom_Warning',
        detail: 'Additional information about warning'
    });
}, 4000);

// Start listening to the process
process.on('warning', (warning) => {

    // If there is a warning then print
    // it and stop the process
    if (warning) {
        console.log(warning);
        process.exit(0);
    }
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 开始…
> 工作…
> 工作…
> 工作…
> (节点:12621)【Custom _ Warning】警告:出事了！
> 关于警告的附加信息
> (使用“节点-跟踪-警告...”显示警告是在哪里创建的)
> 警告:发生了一些事情！
> 超时。_ onTimeout(/home/aditya/Programming/GFG/New/emitwarning . js:9:13)
> at lisontimeout(节点:内部/计时器:556:17)
> at processTimers(节点:内部/计时器:499:7) {
> 代码:【Custom_Warning】，
> 详细信息:【有关警告的其他信息】

**示例 2:** 发出多个警告，并根据警告类型采取措施。

## index.js

```js
console.log("Start ...");

// Use setInterval to keep the process running
setInterval(() => {
    console.log("Working ...");
}, 1000);

setTimeout(() => {
    process.emitWarning('Something happened!', {
        code: 'Custom_Warning',
        detail: 'Additional information about warning'
    });
}, 4000);

setTimeout(() => {
    process.emitWarning('Something needs to be fixed!', {
        type: 'IMPORTANT',
        code: '007',
        detail: 'Can not proceed further!'
    });
}, 6000);

// Start listening to the process
process.on('warning', (warning) => {

    // If there is an important warning
    // stop the process
    // warning.name = type
    if (warning.name === 'IMPORTANT') {
        console.log('Fix this ASAP!')
        process.exit(0);
    }
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 开始…
> 工作…
> 工作…
> 工作…
> (节点:12893)【Custom _ Warning】警告:出事了！
> 关于警告的附加信息
> (使用` node–trace-warnings…`显示警告是在哪里创建的)
> 工作中…
> 工作中…
> (节点:12893) [007]重要提示:有问题需要解决！
> 不能再继续了！
> 尽快修复！

**示例 3:** 将错误对象作为警告而不是字符串传递。请注意，如果正在传递错误对象，则可选参数将被忽略。

## index.js

```js
console.log("Start ...");

// Use setInterval to keep the process running
setInterval(() => {
    console.log("Working ...");
}, 1000);

setTimeout(() => {
    process.emitWarning(new Error('Whoops!'), {
        code: 'Custom_Warning',
        detail: 'Additional information about warning'
    });
}, 4000);

// Start listening to the process
process.on('warning', (warning) => {

    // If there is a warning then print
    // it and stop the process
    if (warning) {
        console.warn(warning);
        process.exit(0);
    }
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 开始…
> 工作…
> 工作…
> 工作…
> (节点:13232)错误:呜呜！
> (使用‘节点-跟踪-警告…’显示警告是在哪里创建的)
> 错误:呜呜！
> 超时。_ onTimeout(/home/aditya/Programming/GFG/New/emitwarning . js:9:25)
> at lisontimeout(节点:内部/定时器:556:17)
> at processTimers(节点:内部/定时器:499:7)

**参考:**[https://nodejs . org/API/process . html # process _ process _ emit warning _ warning _ type _ code _ ctor](https://nodejs.org/api/process.html#process_process_emitwarning_warning_type_code_ctor)