# Node.js vm.runInNewContext()方法

> 原文:[https://www . geesforgeks . org/node-js-VM-runinnewcontext-method/](https://www.geeksforgeeks.org/node-js-vm-runinnewcontext-method/)

**vm.runInNewContext()** 方法对所述的 contextObject 进行上下文化，编译所写的代码并在所创建的上下文中运行它，然后在这一切之后返回输出。但是，运行的代码不能访问本地范围。

**语法:**

```
vm.runInNewContext( code, contextObject, options )
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **代码:**是要编译运行的 JavaScript 代码。
*   **contextObject:** 它是一个将被上下文化的对象，如果未定义，将创建一个新的对象。
*   **选项:**是可选参数，返回*对象*或*字符串*，如果是字符串，则定义返回字符串的文件名。
    保存以下参数:
    1.  **文件名:**它包含一个字符串，该字符串指定了由该脚本生成的堆栈跟踪中使用的文件名。它的默认值是“evalmachine.anonymous”。
    2.  **行号偏移量:**它保存一个数字，该数字指定由该脚本生成的堆栈跟踪中显示的行号的偏移量。它的默认值是 0。
    3.  **列偏移量:**它保存一个数字，该数字指定由该脚本生成的堆栈跟踪中显示的列号的偏移量。它的默认值是 0。
    4.  **displayErrors:** 它保存一个布尔值，即如果在编译代码时引发错误，并且引发错误的代码行链接到堆栈跟踪，则该值为 true。它的默认值为真。
    5.  **超时:**它保存一个整数值，指定在结束执行前执行所述代码所需的毫秒数。但是，如果一个执行被关闭，那么将会发生一个错误，并且这个值必须是一个正整数。
    6.  **breakonsingt:**它保存一个布尔值。如果是真的，那么一提供 *SIGINT* 即(Ctrl+C)就停止执行。如果停止执行，就会抛出一个错误。默认情况下，它的值为 false。
    7.  **contextName:** 它保存一个字符串。它是新生成的上下文的人类可读名称。默认情况下，它是“虚拟机上下文 I”，其中， *i* 是生成的上下文的索引，数字递增。
    8.  **contextOrigin:** 它保存一个字符串。相当于最近生成的上下文的是*原点*。此外，原点必须像网址一样形成。其缺省值为”。
    9.  **contextCodeGeneration:** 为 Object 类型。
        它包含以下参数:

*   **字符串:**它保存一个布尔值，如果它被设置为 false，那么对函数构造函数或 eval 的任何调用都会抛出一个错误，即 *EvalError* 。其默认值为真。
*   **wasm:** 它保存一个布尔值。如果它被设置为假，那么任何试图编译一个网络组件模块的操作都会抛出一个错误，即*网络组件。编译错误*。其缺省值为真。

*   **缓存数据:**它保存一个*缓冲区、一个类型数据区或一个数据视图*。它提供了一个可选的*缓冲区或类型数据区，或数据视图*，以便在 V8 的代码缓存数据的帮助下使用所提供的源。之后，*缓存数据弹出*的值可以设置为真或假。这取决于 V8 对数据的接收。*   **生产计划数据:**它保存一个布尔值。如果是真的并且*缓存数据*不再可用，那么 V8 会尝试输出代码的代码缓存数据。如果实现了这一点，那么就会生成一个包含 V8 代码缓存数据的缓冲区，然后将其存储在虚拟机的*缓存数据*中。正在返回的脚本实例。此外，*缓存数据产生的*值根据代码缓存数据设置为真或假。但是，不推荐使用此选项，而是使用*script . createcacheddata()*。默认情况下，它的值为 false。*   **importModuleDynamically:** It holds a function which is called while evaluating this module when *import()* method is called. And if this option is not stated then the calls to import() will be rejected with an error.
    It holds following parameters:
    *   **说明符:**它保存一个字符串。它是传递给 import()方法的说明符。
    *   **模块:**保存 *vm。模块*。它返回*模块名称空间对象或虚拟机。模块*。

    **返回值:**返回脚本中最后一条语句的执行结果。

    下面的例子说明了在 Node.js 中 **vm.runInNewContext()方法**的使用:

    **例 1:**

    ```
    // Node.js program to demonstrate the     
    // vm.runInNewContext() method

    // Including util and vm module
    const util = require('util');
    const vm = require('vm');

    // Creating contextObject
    const obj = {
      portal: 'GeeksforGeeks',
      authors: 30
    };

    // Calling runInNewContext method
    // with its parameters
    vm.runInNewContext('authors *= 3;', obj);

    // Displays output
    console.log(obj);
    ```

    **输出:**

    ```
    { portal: 'GeeksforGeeks', authors: 90 }

    ```

    这里，输出中的作者是 90 as (30 * 3 = 90)。

    **例 2:**

    ```
    // Node.js program to demonstrate the     
    // vm.runInNewContext() method

    // Including util and vm module
    const util = require('util');
    const vm = require('vm');

    // Creating contextObject
    const contextobj = {localVar: 20};

    // Calling runInNewContext method
    // with its parameters
    var x = vm.runInNewContext('localVar +=(3*3);',
                contextobj, 2, 'myfile.vm');

    // Displays output
    console.log(contextobj);
    console.log(x);
    ```

    **输出:**

    ```
    { localVar: 29 }
    29

    ```

    **参考:**[https://nodejs . org/API/VM . html # VM _ runinnwccontext _ code _ context object _ options](https://nodejs.org/api/vm.html#vm_vm_runinnewcontext_code_contextobject_options)