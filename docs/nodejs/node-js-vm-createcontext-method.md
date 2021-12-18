# Node.js vm.createContext()方法

> 原文:[https://www . geesforgeks . org/node-js-VM-create context-method/](https://www.geeksforgeeks.org/node-js-vm-createcontext-method/)

**vm.createContext()** 方法用于创建一个可以用来运行多个脚本的上下文。此外，如果声明的**上下文对象**被忽略，则返回一个新的、空的**上下文化的**对象。但是，如果陈述了 **contextObject** ，则该方法将准备好该对象，以便它可以用于调用 **vm.runInContext()** 或 **script.runInContext()** 。其中**上下文对象**将是这些脚本中的全局对象，可以保留其活动属性。在脚本之外，它由 vm 模块运行，甚至全局变量也保持不变。

**语法:**

```
vm.createContext( contextObject, options )
```

**参数:**该方法接受两个参数，如下所述:

*   **Context object:** is the object of the upper and lower cultures.
*   **option:** optional, returning *object* .

**返回值:**返回上下文化对象。

下面的例子说明了 **createContext()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// vm.createContext([contextObject[, options]])
// method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Assigning value to the global variable
global.globalVar = 10;

// Defining Context object
const object = { globalVar: 4 };

// Contextifying stated object
// using createContext method
vm.createContext(object);

// Compiling code
vm.runInContext('globalVar /= 2;', object);

// Displays the context
console.log("Context: ", object);

// Dsiplays value of global variable
console.log("Global Variable is ", global.globalVar);
```

**输出:**这里，上下文中的 globalVar 在输出 as 中是 2(4/2 = 2)，但是 globalVar 的值仍然是 10。

```
Context:  { globalVar: 2 }
Global Variable is  10

```

**例 2:**

```
// Node.js program to demonstrate the     
// vm.createContext([contextObject[, options]])
// method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Assigning value to the global variable
global.globalVar = 5;

// Defining Context object
const object = { globalVar: 20 };

// Contextifying stated object
// using createContext method
vm.createContext(object);

// Compiling code
vm.runInContext('globalVar += 2;', object);

// Displays the context
console.log("Context: ", object);

// Dsiplays value of global variable
console.log("Global Variable is ", global.globalVar);
```

**输出:**这里，上下文中的 globalVar 在输出 as 中是 22(20+2 = 22)，但是 globalVar 的值仍然是 5。

```
Context:  { globalVar: 22 }
Global Variable is  5

```

**参考:**[https://nodejs . org/API/VM . html # VM _ create context _ context object _ options](https://nodejs.org/api/vm.html#vm_vm_createcontext_contextobject_options)