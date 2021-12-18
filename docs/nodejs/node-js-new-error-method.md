# Node.js 新错误()方法

> 原文:[https://www.geeksforgeeks.org/node-js-new-error-method/](https://www.geeksforgeeks.org/node-js-new-error-method/)

为了生成和处理错误，Node.js 支持运行应用程序期间出现的许多机制，并且它是一个内置的应用程序，因此我们不导入任何库。Node.js 引发的所有系统错误都继承自 JavaScript 的< *Error* >类，并且提供了该类中最少的可用属性。

**新的 Error()** 方法是 Node 模块的内置应用程序编程接口，在该接口中创建新的 Error 对象，并将 *error.message* 属性设置为所提供的文本消息。通过调用 *message.toString()* ，如果一个对象作为消息传递，就会生成文本消息。另一个属性 *error.stack* 表示代码中调用*新 Error()* 的点，这个属性的堆栈跟踪依赖于 *V8* 的堆栈跟踪 API。

**语法:**

```
new Error(message)
```

**参数:**该功能接受如上所述的单个参数，如下所述:

*   **消息** < *字符串* > **:** 接受抛出错误时控制台显示的消息。

**返回值** < *错误* >:返回作为参数传递的消息值中定义的特定错误。

下面的例子说明了在 Node.js 中使用*新的错误(消息)*方法

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// the new Error() method 

// Creating new Error along with 
// passing an error message
const error = new Error(
'Error Message: Hey geek, Error is working all fine..');

// Printing error message
console.log(error.message);

// Printing error stack
console.log(error.stack);

// Printing the error in console
console.log(error);
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> >>错误信息:嘿，极客，错误工作正常..
> > >错误:错误信息:嘿怪胎，错误没问题..
> 在物体上。<匿名>(C:\ Users \ Vikas Kumar \ Desktop \ test . js:6:15)……..at internal/main/run _ main _ module . js:17:47
> >>错误:错误消息:嘿，极客，错误没问题..
> 在物体上。<匿名>(C:\ Users \ Vikas Kumar \ Desktop \ test . js:6:15)……..at 内部/主/run_main_module.js:17:47

**示例 2:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// the new Error() method 

// Creating new object
const newObjectError = {};

// Creating Errors along with 
// passing error message
const error = new Error(
'Error Message: Hey Geek, Error is working fine...');

const error1 = new Error();
const error2 = new Error();

// Printing the stck trace limit
console.log(">> ", Error.stackTraceLimit);

// Printing error message
console.log(">> ", error.message);

// Printing the error in console
// console.log(error1);

// Another way to create error regarding any object
Error.captureStackTrace(newObjectError);

// Inspecting the error
console.log(">> ", require('util').inspect(error1));

if (error1.stack == newObjectError.stack) {
    console.log(">> ", "Different Errors can be compared");
} else {
    console.log(">> ", "Errors can't be compared");
}

// Comparing two equal Errors
if (error1.stack === error2.stack) {
    console.log(">> ", "Equal Errors can be compared");
} else {
    console.log(">> ", "Errors can't be compared");
}
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> > > 10
> > >错误信息:嘿极客，错误工作正常……
> >>对象出错
> 。<匿名>(C:\ Users \ Vikas Kumar \ Desktop \ test . js:26:16)………..at internal/main/run _ main _ module . js:17:47
> >>错误无法比较
> > >错误无法比较

**参考:**T2】https://nodejs.org/api/errors.html#errors_new_error_message