# node . js util . deverate()方法

> 原文:[https://www . geeksforgeeks . org/node-js-util-defer ate-method/](https://www.geeksforgeeks.org/node-js-util-deprecate-method/)

**util . deverate()**(在 v0.8.0_ method 中添加)是 util 模块的内置应用程序编程接口，它以标记为弃用的方式包装 **fn** (可能是函数或类)。当调用**util . defense()**方法时，它返回一个使用“警告”事件发出 defense warning 的函数。第一次调用返回的函数时，会发出警告并打印到 stderr。一旦发出警告，就调用包装函数。如果在对“*util . deverate()*的多次调用中提供了相同的可选代码，则仅发出一次警告。

**语法:**

```
util.deprecate(fn, msg, )
```

**参数:**该函数接受三个参数，如上所述，如下所述:

*   **fn:** 被弃用的是<功能>。
*   **消息:**当不推荐使用的功能被调用时，需要显示一个“警告消息”<字符串>。
*   **代码:**是一个折旧代码<字符串>，与折旧警告一起打印。一些[不推荐使用的原料药](https://nodejs.org/api/deprecations.html#deprecations_revoking_deprecations)是 DEP0001，DEP0001，…，DEP0143。

**返回值:**返回包装后发出警告的弃用函数，即运行完整函数后，警告消息与弃用的 API 一起返回。

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// util.deprecate() method 

// Import the util module 
var util = require('util');

var depricateFunction = util.deprecate(

    // Function which is depricated
    function () { },

    // Warning message that is 
    // printed to stderr
    "someWarningMessage",

    // Deprecated API
    'Deprication API'
);

// Function call
depricateFunction();
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
[Deprication API] DepricationWarning: someWarningMessage

```

**示例 2:** **文件名:index.js**

```
// Node.js program to demonstrate the 
// util.deprecate() method 

// Import the util module 
var util = require('util');
var outerValue = "along with"

var geekyFunction1 = util.deprecate(() => {
    console.log("This Depricated function is working, ");
},
    // The arrow function which is depricated
    "geekyFunction() is deprecated. Use "
        + "geeksForGeeksFunction() instead",

    // The warning message that is printed
    // to stderr
    'DEP0014' // Deprecated API
);

var geekyFunction2 = util.deprecate(function (call) {
    console.log("This Depricated function is working, ", 
            outerValue, call());
},
    // The function which is depricated
    "geekyFunction() is deprecated. Use "
        + "geeksForGeeksFunction() instead",
    // The warning message that is printed to stderr
    'DEP0014' // Deprecated API
);

// Function call
geekyFunction1();

// Function call
geekyFunction2(function call() {
    console.log("Callback");
    return "return value"
});
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 该取消函数正在工作，
> 回调
> 该取消函数正在工作，返回值
> 【dep 0014】弃用警告:geekyFunction()已弃用。请改用 geeksforgeeksFunction()

**条件:**

*   如果为*进程设置了*跟踪-折旧/跟踪-警告* cmd 标志，则第一次将堆栈跟踪和警告打印到 stderr。跟踪折旧*属性设置为*真*。
*   如果设置了*–抛出-弃用* cmd 标志，或者*进程.抛出弃用*设置为*真*，则会抛出异常。
*   如果将*进程.节点预定义*属性设置为真，或者使用*不折旧/不警告* cmd 标志，则**实用折旧()**不执行任何操作。
*   *跟踪折旧*和*进程.跟踪折旧的优先级低于–抛出折旧* cmd 标志和*进程.抛出折旧*属性。

**参考:**[https://nodejs . org/API/util . html # util _ util _ deprecate _ fn _ msg _ code](https://nodejs.org/api/util.html#util_util_deprecate_fn_msg_code)