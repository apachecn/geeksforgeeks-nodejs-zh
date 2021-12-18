# node . js 中的导入导出

> 原文:[https://www.geeksforgeeks.org/import-and-export-in-node-js/](https://www.geeksforgeeks.org/import-and-export-in-node-js/)

导入和导出文件是任何编程语言的重要部分。导入函数或模块增强了代码的可重用性。当应用程序变大时，维护一个包含所有功能和逻辑的文件变得很困难。也阻碍了调试的进程。因此，最好为特定的函数创建单独的文件，然后根据需要导入它们。

Node.js 还允许导入和导出函数和模块。一个模块中的函数可以在其他模块中导入和调用，从而节省了将函数定义复制到其他文件中的工作量。该模块可以单独编辑或调试，从而更容易添加或删除功能。

**包含其他文件功能的步骤:**

1.  **创建模块:**模块是在 Node.js 中创建的，是 JavaScript 文件。**每次都有新文件。js** 扩展被创建，它变成了一个模块。
2.  **导出模块:** **文件名:func.js**

```js
function add(x, y) {
   return x + y;
}

function subtract(x, y) {
   return x - y;
}

// Adding the code below to allow importing
// the functions in other files
module.exports = { add }
```

*   **Importing a Module:** We need to import the module to use the functions defined in the imported module in another file. The result returned by require() is stored in a variable which is used to invoke the functions using the dot notation.
    **Filename: main.js**

    ```js
    // Importing the func.js module

    // The ./ says that the func module
    // is in the same directory as 
    // the main.js file
    const f = require('./func');

    // Require returns an object with add()
    // and stores it in the f variable 
    // which is used to invoke the required 

    const result = f.add(10, 5);

    console.log('The result is:', result);
    ```

    **输出:**

    ```js
    The result is: 15
    ```

    **从本地文件导入多个功能:** **文件名:func.js**

    ```js
    function add(x, y) {
      return x + y;
    }

    function subtract(x, y) {
      return x - y;
    }

    module.exports = { add, subtract};
    ```

    **文件名:main.js**

    ```js
    const f = require('./func');

    console.log(f.add(4, 4));
    console.log(f.subtract(8, 4));
    ```

    我们还可以使用析构语法来解包 require()函数返回的对象的属性，并将它们存储在各自的变量中。

    ```js
    const { add, subtract} = require('./func');
    console.log(add(4, 4)); 
    console.log(subtract(8, 4)); 
    ```

    **输出:**

    ```js
    8
    4

    ```

    **导出模块的其他方式**

    *   定义模块内部的函数。导出对象。

        ```js
        module.exports = {
          add: function (x, y) {
            return x + y;
          },

          subtract: function (x, y) {
            return x - y;
          },
        };
        ```

    *   将每个功能独立定义为一个模块方法。导出

        ```js
        module.exports.add = function (x, y) {
           return x + y;
        };

        module.exports.subtract = function (x, y) {
           return x - y;
        };
        ```

    **从目录中导入模块:**通过在 lib.js 前面加上目录名，在目录中导入 lib.js 文件。

    ```js
    const lib = require('./mod/lib');

    console.log(lib.add(6, 4));
    console.log(lib.subtract(12, 4));
    ```

    **node . js 中有三种类型的模块**

    1.  **从本地模块导入:**这些模块由用户创建，可以导入为:

        ```js
        const var = require('./filename.js'); // OR
        const var = require('./path/filename.js');

        ```

    2.  **从核心模块导入:**这些模块内置在 Node.js 中，可以导入为:

        ```js
        const var = require('fs');
        ```

    3.  **从第三方模块导入:**这些模块是使用包管理器(如 npm)安装的。第三方模块的例子有 express、mongoose、nodemon 等。这些导入为:

        ```js
        const express = require('express');
        ```

    因此，上面是几个在 Node.js 中从不同文件导入和导出函数的例子。