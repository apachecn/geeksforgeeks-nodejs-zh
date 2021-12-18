# Node.js console.debug()方法

> 原文:[https://www.geeksforgeeks.org/node-js-console-debug-method/](https://www.geeksforgeeks.org/node-js-console-debug-method/)

**console.debug()方法**是控制台模块的内置应用编程接口，用于将消息以换行符打印到 stdout。类似于 console.log()方法。

**语法:**

```js
console.debug(data, args);
```

**参数:**该方法有两个参数，如上所述，如下所述:

1.  **Data:** This parameter specifies the data to be printed.
2.  **Parameter:** is an optional parameter, which specifies the parameter passed as a substitute value in the message passed to data. All passed parameters are sent to util.format ().

**返回值:**这个方法不返回任何东西，而是用换行符将格式化的消息打印到 stdout。

下面的例子说明了在 Node.js 中使用 console.debug()方法:

**示例 1:** **文件名:app.js**

```js
// Accessing console module
const console = require('console');

// Calling console.debug() 
console.debug("This is a sample debug message!");
console.debug("Sample debug message with args: %d", 39);
```

使用以下命令运行 app.js 文件:

```js
node app.js
```

**输出:**

```js
This is a sample debug message!
Sample debug message with args: 39

```

**示例 2:** **文件名:app.js**

```js
// Accessing console module
const console = require('console');

// Calling console.debug()
console.debug("This is a %s", 
    " sample debug message!");
console.debug("Sample debug message"
    + " with args: %d", 34);
console.debug("Debug message: Warning "
    + "at function %s: line number %d ",
    "ff()",96)

var isDebugMode = true;
console.custom_debug = function(message) { 
  if (isDebugMode) {
    console.log(message);
  }
}

console.custom_debug("Custom debug message");
```

使用以下命令运行 app.js 文件:

```js
node app.js
```

**输出:**

```js
This is a  sample debug message!
Sample debug message with args: 34
Debug message: Warning at function ff(): line number 96
Custom debug message

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/console . html # console _ console _ debug _ data _ args](https://nodejs.org/api/console.html#console_console_debug_data_args)