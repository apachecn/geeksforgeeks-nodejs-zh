# node . js require 和 ES6 导入导出的区别

> 原文:[https://www . geesforgeks . org/node-js-require-and-es6-import-export/](https://www.geeksforgeeks.org/difference-between-node-js-require-and-es6-import-and-export/)之间的差异

Node.js 遵循 commonJS 模块系统，它要求包含存在于单独文件中的模块，为此，它有像**【require】****【ES6 导入和导出】**这样的方法在 node.js 中可用。

**Require:** 它是内置函数，包含独立文件中存在的模块是最简单的方法。require 的基本功能是读取一个 JavaScript 文件，执行该文件，然后返回导出对象。它不仅允许您添加内置的核心节点模块，还允许您在所需的程序中添加基于社区的模块(node_modules)和本地模块。像–**HTTP 模块**、 **URL 模块**、**查询字符串模块**、**路径模块**等节点中有各种内置模块。

**语法:**

*   The built-in modules are as follows:

    ```js
    const express = require('express');
    ```

*   Include local modules as follows. For example, you need the "abc" module, but do not specify the path.

    ```js
    require('abc');
    ```

**示例:**节点将依次在 module.paths 指定的所有路径中查找**。**

*   **输入:**

    ```js
    require('abc');
    ```

*   **输出:**
    *   **如果节点找不到:**

        ```js
        Error: Cannot find module 'abc'
            at Function.Module._resolveFilename (module.js:470:15)
            at Function.Module._load (module.js:418:25)
            at Module.require (module.js:498:17)
            at require (internal/module.js:20:19)
            at repl:1:1
            at ContextifyScript.Script.runInThisContext (vm.js:23:33)
            at REPLServer.defaultEval (repl.js:336:29)
            at bound (domain.js:280:14)
            at REPLServer.runBound [as eval] (domain.js:293:12)
            at REPLServer.onLine (repl.js:533:10)
        ```

    *   **如果节点找到它:**

        ```js
        // It is the content of the file
        Geeksforgeeks example for require
        ```

**ES6 导入&导出:**此语句用于引用一个专家系统模块。其他文件类型不能用这些语句导入。它们仅在 ES 模块中被允许，并且该语句的说明符可以是 URL 样式的相对路径或包名。

而 **Export** 语句允许用户将其创建的对象和方法导出到其他程序。例如，如果您分配了一个字符串文字，那么它会将该字符串文字公开为一个模块。

**语法:**

*   Used to import files.

    ```js
    // Importing submodule from 
    // 'es-module-package/private-module.js';
    import './private-module.js';
    ```

*   Used to export files.

    ```js
    module.exports = 'A Computer Science Portal';
    ```

**示例:**创建两个 JS 文件一个用于导入，另一个用于导出，或者您可以使用任何模块进行导入，这样就不需要导出一个。

*   **导出**文件名`Message.js`

    ```js
    // Exporting module
    module.exports = 'Hello Geek';
    ```

    **导入**文件名`Display.js`

    ```js
    // Importing module
    var msg = import('./Message.js');
    console.log(msg);</li>

        <li><strong>Output:</strong>
    <div class="noIdeBtnDiv">

    Hello Geek
    ```

**node . js require 和 ES6 导入导出的区别:**虽然 require 函数和 ES6 导入导出有很多共同点，在代码上看起来执行相同的功能，但是在很多方面是不同的。T32】T33

| 需要 | ES6 导入和导出 |
| REQUIRE is non-lexical, it stays where they have put the file. | Import is lexical, and it is sorted to the top of the file. |
| It can be called anytime, anywhere in the program. | Can't be called conditionally, always run at the beginning of the file. |
| You can run the code directly with the require statement. | To run a program containing import statements, you must use the experimental module feature flag. |
| If you want to use the require module, you must use' Save File'. Js' extension. | If you want to use the import module, then you must use the save file. Mjs' extension. |

**注意:**您必须注意，在您的节点程序中不能同时使用 require 和 import，更优选使用 require 而不是 import，因为您需要使用实验模块标志功能来运行 import 程序。