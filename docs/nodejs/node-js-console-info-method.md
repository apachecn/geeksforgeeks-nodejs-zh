# Node.js console.info()方法

> 原文:[https://www.geeksforgeeks.org/node-js-console-info-method/](https://www.geeksforgeeks.org/node-js-console-info-method/)

**console.info()方法**是控制台模块的内置应用编程接口，用于将消息以换行符打印到 stdout。它类似于 console.log()方法。

**语法:**

```js
console.info(data, args);
```

**参数:**该方法有两个参数，如上所述，描述如下:

*   **数据:**此参数指定要打印的数据。
*   **参数:**是可选参数，指定在传递给数据的消息中作为替代值传递。所有传递的参数都被发送到 util.format()。

**返回值:**这个方法不返回任何东西，而是用换行符将格式化的消息打印到 stdout。

下面的例子说明了在 Node.js 中 console.info()方法的使用:

**示例 1:** **文件名:app.js**

```js
// Node.js program to demonstrate the   
// console.info() method

// Accessing console module
const console = require('console');

// Calling console.info() method
console.info("this is a sample info message!");
console.info("sample info message with args: %d", 39);
```

使用以下命令运行 app.js 文件:

```js
node app.js
```

**输出:**

```js
this is a sample info message!
sample info message with args: 39

```

**示例 2:**
**文件名:app.js**

```js
// Node.js program to demonstrate the   
// console.info() method

// Accessing console module
const console = require('console');

// Calling console.info() method
console.info("this is a %s" +
    " sample info message!");

console.info("sample info message "
    + "with args: %d", 34);
console.info("info message: Warning "
    + "at function %s: line number"
    + " %d ff()", 96)

var isDebugMode = true;
console.custom_info = function (message) {
    if (isDebugMode) {
        console.log(message);
    }
}

console.custom_info("custom info message");
```

使用以下命令运行 app.js 文件:

```js
node app.js
```

**输出:**

```js
this is a  sample info message!
sample info message with args: 34
info message: Warning at function ff(): line number 96
custom info message

```

**注意:**以上程序使用`node filename.js`命令编译运行。

**参考:**[https://nodejs . org/API/console . html # console _ console _ info _ data _ args](https://nodejs.org/api/console.html#console_console_info_data_args)