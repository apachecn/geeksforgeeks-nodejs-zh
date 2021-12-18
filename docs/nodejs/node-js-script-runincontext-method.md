# Node.js script.runInContext()方法

> 原文:[https://www . geesforgeks . org/node-js-script-runin context-method/](https://www.geeksforgeeks.org/node-js-script-runincontext-method/)

方法用于运行存在于*虚拟机中的编译代码。在所述*上下文对象*内编写*对象的脚本并返回输出。但是，运行的代码无法访问本地范围。

**语法:**

```js
script.runInContext( contextifiedObject, options )
```

**参数:**这个方法接受两个参数，如上所述，如下所述:

*   **Contextualized object:** It is a *contextualized* object returned by vm.createContext () method.
*   **option:** is an optional parameter, which returns the object. It contains the following parameters:
    1.  [T0】 displayErrors: 【T1] It contains a Boolean value, that is, if an error is raised when compiling the code, and the line of code that caused the error is linked to the stack trace, the value is true. Its default value is true.
    2.  **Timeout:** It holds an integer value that specifies the number of milliseconds required to execute the code before ending execution. However, if the execution is turned off, an error will occur. This value must definitely be a positive integer.
    3.  **break on origint:** It holds a Boolean value. If true, the execution will be stopped once *sigint* (i.e. Ctrl+C) is provided, and if the execution is stopped, an error will be thrown. By default, its value is false.

**返回值:**返回脚本中最后一条语句的执行结果。

下面的例子说明了在 Node.js 中 **script.runInContext()方法**的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// script.runInContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Constructing context
const contextobj = {
  name: 'Nidhi',
  articles: 60
};

// Constructing script
const script = new vm.Script('articles *= 10;');

// Contextifying object
vm.createContext(contextobj);

// Calling runInContext method
script.runInContext(contextobj);

// Displays output
console.log(contextobj);
```

**输出:**

```js
{ name: 'Nidhi', articles: 600 }

```

这里，文章是 600 as (60*10 = 600)。

**例 2:**

```js
// Node.js program to demonstrate the     
// script.runInContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Constructing context
const contextobj = { globalVar: 6 };

// Constructing script
const script = new vm.Script('globalVar += 12;');

// Contextifying object
vm.createContext(contextobj);

// Calling for loop
for (let i = 1; i < 4; i++) {

// Calling runInContext method
script.runInContext(contextobj);
}

// Displays output
console.log("The output is: ", contextobj);
```

**输出:**

```js
The output is:  { globalVar: 42 }

```

**参考:**[https://nodejs . org/API/VM . html # VM _ script _ runincontext _ context object _ options](https://nodejs.org/api/vm.html#vm_script_runincontext_contextifiedobject_options)