# Node.js assert.match()函数

> 原文:[https://www . geesforgeks . org/node-js-assert-match-function/](https://www.geeksforgeeks.org/node-js-assert-match-function/)

assert 模块提供了一组用于验证不变量的断言函数。 **assert.match()** 函数期望字符串输入与正则表达式匹配。如果条件为真，则不会产生输出，否则会引发断言错误。

**语法:**

```js
assert.match(string, regexp[, message])
```

**参数:**该功能接受如下参数，如上所述，如下所述:

*   **字符串:**此参数保存需要求值的字符串值。它是字符串类型。
*   **正则表达式:**该参数是与给定字符串值匹配的正则表达式。
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
    assert.match('I will try to pass', /fail/);
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

    > 错误:AssertionError [ERR_ASSERTION]:输入与常规的
    > 表达式不匹配/fail/。输入:
    > 
    > 我会努力通过的
    > 
    > 在对象。<anonymous>(C:\ Users \ Lenovo \ Downloads \ index . js:14:12)
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
    assert.match('I am good', /good/);
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

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ match _ string _ regexp _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_match_string_regexp_message)