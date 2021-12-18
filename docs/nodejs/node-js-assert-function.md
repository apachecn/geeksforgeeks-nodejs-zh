# Node.js assert()函数

> 原文:[https://www.geeksforgeeks.org/node-js-assert-function/](https://www.geeksforgeeks.org/node-js-assert-function/)

assert 模块提供了一组用于验证不变量的断言函数。在 **assert()函数**中，如果值不是真，则抛出一个 AssertionError，消息属性设置为等于消息参数的值。

**语法:**

```js
assert(value[, message])
```

**参数:**该功能接受如下参数，如上所述，如下所述:

*   **值:**此参数保存需要求值的表达式。它是任何类型的。
*   **消息:**此参数保存字符串或错误类型的错误消息。这是一个可选参数。

**返回值:**该函数返回对象类型的断言错误。

**安装 assert 模块:**

1.  You can visit the link to [Install assert module](https://www.npmjs.com/package/assert). You can install this package by using this command.

    ```js
    npm install assert
    ```

    **注意:**安装是可选步骤，因为它内置了 Node.js 模块。

2.  安装断言模块后，您可以使用命令在命令提示符下检查您的**断言**版本。

    ```js
    npm version assert
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js，如下所示。

**示例 1:** **文件名:index.js**

```js
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert(0)
} catch(error) {
    console.log("Error:", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  Run **index.js** file using below command:

    ```js
    node index.js
    ```

    **输出:**

    > 错误:AssertionError [ERR_ASSERTION]:表达式被评估为错误值:
    > 
    > 断言(0)
    > 
    > 在对象。<anonymous>(C:\ Users \ Lenovo \ Downloads \ index . js:6:5)
    > at Module。_ 编译(内部/模块/cjs/loader.js:1138:30)
    > 在对象.模块. _ 扩展..js(internal/modules/cjs/loader . js:1158:10)
    > at module . load(internal/modules/cjs/loader . js:986:32)
    > at function . module . _ load(internal/modules/cjs/loader . js:879:14)
    > at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
    > at internal/main/run _ main _ main</anonymous>

**示例 2:** **文件名:index.js**

```js
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert(1)
    console.log("No Error Occured")
} catch(error) {
    console.log("Error:", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  Run **index.js** file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    No Error Occured

    ```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ value _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_value_message)