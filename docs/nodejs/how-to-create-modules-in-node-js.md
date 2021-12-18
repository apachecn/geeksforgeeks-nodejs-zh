# 如何在 Node.js 中创建模块？

> 原文:[https://www . geesforgeks . org/如何在节点中创建模块-js/](https://www.geeksforgeeks.org/how-to-create-modules-in-node-js/)

模块是一个单独的逻辑文件中的 JavaScript 代码的集合，可以根据它们的相关功能在外部应用程序中使用。模块很受欢迎，因为它们易于使用且可重用。

要在 Node.js 中创建一个模块，需要**导出**关键字。这个关键字告诉 Node.js 这个函数可以在模块外使用。

**语法:**

```
exports.function_name = function(arg1, arg2, ....argN) {
    // function body
};  

```

**自定义节点模块示例:**

*   **创建要导出的文件**

    ```
    // File name: calc.js

    exports.add = function (x, y) {
        return x + y;
    };

    exports.sub = function (x, y) {
        return x - y;
    };

    exports.mult = function (x, y) {
        return x * y;
    };

    exports.div = function (x, y) {
        return x / y;
    };
    ```

*   **使用‘要求’关键字导入文件**

    ```
    // File name: App.js
    var calculator = require('./calc');

    var x = 50, y = 20;

    console.log("Addition of 50 and 20 is "
                       + calculator.add(x, y));

    console.log("Subtraction of 50 and 20 is "
                       + calculator.sub(x, y));

    console.log("Multiplication of 50 and 20 is "
                       + calculator.mult(x, y));

    console.log("Division of 50 and 20 is " 
                       + calculator.div(x, y));
    ```

*   **输出:**

    ```
    Addition of 50 and 20 is 70
    Subtraction of 50 and 20 is 30
    Multiplication of 50 and 20 is 1000
    Division of 50 and 20 is 2.5

    ```