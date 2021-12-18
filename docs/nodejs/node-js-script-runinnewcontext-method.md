# node . js script . runinnewcontext()方法

> 原文:[https://www . geesforgeks . org/node-js-script-runinnewcontext-method/](https://www.geeksforgeeks.org/node-js-script-runinnewcontext-method/)

**script.runInNewContext()** 方法首先对所述的 contextObject 进行上下文化，在 vm 内部运行编译后的代码。创建上下文中的脚本对象，然后返回输出。但是，运行的代码无法访问本地范围。

**语法:**

```
script.runInNewContext( contextObject, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **contextObject:** 它是一个将被上下文化的对象，如果没有定义，那么将创建一个新的对象，
*   **options:** It is optional and returns *Object*.

    它包含以下参数:

    1.  **displayErrors:** 它保存一个布尔值，即如果在编译代码时引发错误，并且引发错误的代码行链接到堆栈跟踪，则该值为 true。其缺省值为真。
    2.  **超时:**它保存一个整数值，指定在结束执行前执行所述代码所需的毫秒数。但是，如果执行被关闭，将会出现错误。这个值绝对必须是正整数。
    3.  **breakonsingt:**它保存一个布尔值。如果是真的，那么一提供 *SIGINT* 即(Ctrl+C)就停止执行。如果停止执行，就会抛出一个错误。默认情况下，它的值为 false。
    4.  **contextName:** 它保存一个字符串。它是新生成的上下文的人类可读名称。默认情况下，它是“虚拟机上下文 I”，其中， *i* 是生成的上下文的索引，数字递增。
    5.  **contextOrigin:** 它保存一个字符串。相当于最近生成的上下文的是*原点*。此外，原点必须像网址一样形成。其缺省值为”。
    6.  **contextCodeGeneration:** 为 Object 类型。
        它包含以下参数:

    *   **字符串:**它保存一个布尔值，如果它被设置为 false，那么对函数构造函数或 eval 的任何调用都会抛出一个错误，即 *EvalError* 。其默认值为真。
    *   **wasm:** 它保存一个布尔值，如果它被设置为 false，那么任何试图编译网络组件模块的操作都会抛出一个错误，即*网络组件。编译错误*。其缺省值为真。

**返回值:**返回脚本中最后一条语句的执行结果。

以下示例说明了在 Node.js 中使用 **script.runInNewContext()方法**:

**例 1:**

```
// Node.js program to demonstrate the     
// script.runInNewContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Constructing context
const context = { x: 3, y:4 };

// Constructing a script
const script = new vm.Script('x *=11, y *=4;');

// Calling runInNewContext method
script.runInNewContext(context);

// Displays output
console.log("The output is: ", context);
```

**输出:**

```
The output is:  { x: 33, y: 16 }

```

**例 2:**

```
// Node.js program to demonstrate the     
// script.runInNewContext() method

// Including util and vm module
const util = require('util');
const vm = require('vm');

// Creating contexts
cont = {
      animal: 'dog',
      total_number: 5
    };

// Creating script with its parameters
var script = vm.createScript(
    'total_number += 5; name = "Sheru"', 'file.vm');

// Calling runInNewContext method
script.runInNewContext(cont);

// Displays output
console.log(cont);
```

**输出:**

```
{ animal: 'dog', total_number: 10, name: 'Sheru' }

```

**参考:**[https://nodejs . org/API/VM . html # VM _ script _ runinnwccontext _ context object _ options](https://nodejs.org/api/vm.html#vm_script_runinnewcontext_contextobject_options)