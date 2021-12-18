# Node.js vm.runInContext()方法

> 原文:[https://www . geesforgeks . org/node-js-VM-runin context-method/](https://www.geeksforgeeks.org/node-js-vm-runincontext-method/)

使用 **vm.runInContext()方法**编译代码。它在 contextifiedObject 的上下文中运行代码，然后返回输出。此外，运行的代码不能访问本地范围，并且 *contextifiedObject* 对象以前是使用 vm.createContext()方法进行上下文化的。

**语法:**

```
vm.runInContext( code, contextifiedObject, options )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **代码:**是要编译运行的 JavaScript 代码。
*   **contextifiedObject:** 编译运行代码时作为全局。
*   **选项:**是保存*对象*或*字符串*的可选参数，如果是字符串，则定义返回字符串的文件名。
    保存以下参数:
    1.  **文件名:**它包含一个字符串。它指定由该脚本生成的堆栈跟踪中使用的文件名。它的默认值是“evalmachine.anonymous”。
    2.  **行号偏移量:**它保存一个数字，该数字指定由该脚本生成的堆栈跟踪中显示的行号的偏移量。其默认值为 0。
    3.  **列偏移量:**它保存一个数字，该数字指定由该脚本生成的堆栈跟踪中显示的列号的偏移量。其默认值为 0。
    4.  **displayErrors:** 如果在编译代码时引发错误，并且引发错误的代码行链接到堆栈跟踪，则该值为布尔值，即 true。其缺省值为真。
    5.  **超时:**它保存一个整数，该整数指定在结束执行之前执行所述代码所需的毫秒数。但是，如果执行被关闭，将会出现错误。这个值绝对必须是正整数。
    6.  **breakon init:**它持有一个布尔值。如果是真的，那么一提供 *SIGINT* 即(Ctrl+C)就停止执行。如果停止执行，就会抛出一个错误。默认情况下，它的值为 false。
    7.  **缓存数据:**它保存一个*缓冲区、一个类型数据区或一个数据视图*。它提供了一个可选的*缓冲区或类型数据区，或数据视图*，以便在 V8 的代码缓存数据的帮助下使用所提供的源。之后，*缓存数据弹出*的值可以设置为真或假。这取决于 V8 对数据的接收。
    8.  **生产计划数据:**它保存一个布尔值。如果是真的并且*缓存数据*不再可用，那么 V8 会尝试输出代码的代码缓存数据。如果实现了这一点，那么就会生成一个包含 V8 代码缓存数据的缓冲区，然后将其存储在虚拟机的*缓存数据*中。正在返回的脚本实例。此外，*缓存数据产生的*值根据代码缓存数据设置为真或假。但是，不推荐使用此选项，而是使用*script . createcacheddata()*。默认情况下，它的值为 false。
    9.  **import moduled dynamic:**当调用 *import()* 方法时，它保存一个在评估该模块时调用的函数。如果没有说明这个选项，那么对 import()的调用将被拒绝，并出现一个错误。
        它包含以下参数:

1.  **说明符:**它保存一个字符串。它是传递给 import()方法的说明符。
2.  **模块:**保存 *vm。模块*。它返回*模块名称空间对象或虚拟机。模块*。

**返回值:**返回脚本中最后一条语句的执行结果。

下面的例子说明了 **vm.runInContext()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the     
// vm.runInContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Defining Context object
const contextobj = { count: 8 }

// Contextifying stated object
// using createContext method
vm.createContext(contextobj);

// Compiling code by using runInContext
// method with its parameter
vm.runInContext('count *= 4;', contextobj, 'file.vm');

// Displays output
console.log("The output is: ", contextobj);
```

**输出:**

```
The output is:  { count: 32 }

```

这里，输出为 32(8 * 4 = 32)。

**例 2:**

```
// Node.js program to demonstrate the     
// vm.runInContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Creating object
cobj = {
         name_of_school: 'M.B.V',
         number_of_students: 10
    },

// Contexifying object
context = vm.createContext(cobj);

// Calling runInContext method
vm.runInContext('number_of_students *= 3;',
             cobj, 'myfile.vm');

// Displays object
console.log(cobj);
```

**输出:**

```
{ name_of_school: 'M.B.V', number_of_students: 30 }

```

**参考:**[https://nodejs . org/API/VM . html # VM _ runincontext _ code _ context object _ options](https://nodejs.org/api/vm.html#vm_vm_runincontext_code_contextifiedobject_options)