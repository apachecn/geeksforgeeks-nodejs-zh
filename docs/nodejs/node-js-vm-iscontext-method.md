# Node.js vm.isContext()方法

> 原文:[https://www.geeksforgeeks.org/node-js-vm-iscontext-method/](https://www.geeksforgeeks.org/node-js-vm-iscontext-method/)

**vm.isContext()方法**是 vm 模块的内置应用编程接口，用于检查所述对象是否正在使用 *vm.createContext()* 方法进行*上下文化*。

**语法:**

```js
vm.isContext( object )
```

**参数:**此方法接受单参数**对象**。

**返回值:**如果所述对象正在被*上下文化*则返回真，否则返回假。

下面的例子说明了在 Node.js 中 **vm.isContext()方法**的使用:

**例 1:**

```js
// Node.js program to demonstrate the     
// vm.isContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Assigning value to the global variable
global.globalVar = 7;

// Defining Context object
const object = { globalVar: 3 };

// Contextifying stated object
// using createContext method
vm.createContext(object);

// Compiling code
vm.runInContext('globalVar *= 6;', object);

// Displays the context
console.log(object);

// Dsiplays value of global variable
console.log(global.globalVar);

// Calling isContext method
vm.isContext(object);
```

**输出:**

```js
{ globalVar: 18 }
7
true

```

这里，上下文中的全局变量输出为 18(6 * 3 = 18)，但全局变量的值仍然是 7。此外，这里陈述的对象被上下文化，所以返回真。

**例 2:**

```js
// Node.js program to demonstrate the     
// vm.isContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Assigning value to the global variable
global.globalVar = 7;

// Defining Context object
const object = { globalVar: 3 };

// Displays the context
console.log(object);

// Dsiplays value of global variable
console.log(global.globalVar);

// Calling isContext method
vm.isContext(object);
```

**输出:**

```js
{ globalVar: 3 }
7
false

```

这里，陈述的对象没有上下文，所以返回 false。

**参考:**T2】https://nodejs.org/api/vm.html#vm_vm_iscontext_object