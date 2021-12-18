# node . js assert . do not match()函数

> 原文:[https://www . geesforgeks . org/node-js-assert-do not match-function/](https://www.geeksforgeeks.org/node-js-assert-doesnotmatch-function/)

assert 模块提供了一组用于验证不变量的断言函数。函数的作用是:字符串输入与正则表达式不匹配。如果条件为真，则不会产生输出，否则会引发断言错误。

**语法:**

```js
assert.doesNotMatch(string, regexp[, message])
```

**参数:**该功能接受三个参数，如上所述，描述如下:

*   **字符串:**此参数保存需要求值的字符串。
*   **正则表达式**该参数保存匹配的正则表达式。
*   **消息**该参数保存字符串或错误类型的错误消息。这是一个可选参数。

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
    assert.doesNotMatch('I will try to pass', /fail/);
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

**示例 2:** **文件名:index.js**

```js
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.doesNotMatch('I will try to pass', /pass/);
    //console.log("No Error Occured")
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
    Error: AssertionError [ERR_ASSERTION]: The input was expected to not match the 
    regular expression /pass/. Input:

    'I will try to pass'

        at Object. (C:\Users\Lenovo\Downloads\index.js:6:12)
        at Module._compile (internal/modules/cjs/loader.js:1138:30)
        at Object.Module._extensions..js (internal/modules/cjs/loader.js:1158:10)
        at Module.load (internal/modules/cjs/loader.js:986:32)
        at Function.Module._load (internal/modules/cjs/loader.js:879:14)
        at Function.executeUserEntryPoint [as runMain] 
            (internal/modules/run_main.js:71:12)
        at internal/main/run_main_module.js:17:47 {
      generatedMessage: true,
      code: 'ERR_ASSERTION',
      actual: 'I will try to pass',
      expected: /pass/,
      operator: 'doesNotMatch'
    } 
    ```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ do notmatch _ string _ regexp _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_doesnotmatch_string_regexp_message)