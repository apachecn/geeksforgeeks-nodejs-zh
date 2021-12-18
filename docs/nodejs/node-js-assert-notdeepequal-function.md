# Node.js assert.notDeepEqual()函数

> 原文:[https://www . geesforgeks . org/node-js-assert-notdeepequal-function/](https://www.geeksforgeeks.org/node-js-assert-notdeepequal-function/)

assert 模块提供了一组用于验证不变量的断言函数。 **assert.notDeepEqual()** 函数测试实际参数和预期参数之间的严格不等式。如果条件为真，则不会产生输出，否则会引发断言错误。
**语法:**

```
assert.notDeepEqual(actual, expected[, message])
```

**参数:**该功能接受如下参数，如上所述，如下所述:

*   **实际:**此参数保存需要评估的实际值。它是任何类型的。
*   **预期:**此参数保存与实际值匹配的预期值。它是任何类型的。
*   **消息:**此参数保存字符串或错误类型的错误消息。这是一个可选参数。

**返回值:**该函数返回对象类型的断言错误。

**安装 assert 模块:**

1.  您可以访问[安装断言模块](https://www.npmjs.com/package/assert)的链接。您可以使用此命令安装此软件包。

    ```
    npm install assert
    ```

2.  **注意:**安装是可选步骤，因为它内置了 Node.js 模块。
3.  安装断言模块后，您可以使用命令在命令提示符下检查您的**断言**版本。

    ```
    npm version assert
    ```

4.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js，如下所示。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.notDeepEqual({ a: '5' }, { a: '5' });
} catch(error) {
    console.log("Error: ", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 **index.js** 文件:
    T0】
3.  **输出:**

    > 错误:AssertionError[ERR _ ASSIGNATE]:预期的"实际"不是严格意义上的深度-等于:
    > 
    > {
    > a:【5】
    > }
    > 
    > 在对象(C:\ user \ Lenovo \ Downloads \ index。js:14:12)
    > 在模块。_ 在对象.模块. _ 扩展处编译（内部/模块/cjs/loader.js:1138:30)
    > ..js(内部/模块/cjs/加载器。js:1158:10)
    > at 模块。加载(内部/模块/cjs/加载器。js:986:32)
    > at 功能。模块。_ 加载(内部/模块/cjs/加载器。js:879:14)
    > at 功能。executeuserentrypoint[as RunMain](内部/模块/run _ main。js:71:12)
    > 在内部/主/run _ main _ main

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.notDeepEqual({ a: '5' }, { a: '11' });
    console.log("No Error Occured")
} catch(error) {
    console.log("Error: ", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 **index.js** 文件:

    ```
    node index.js
    ```

3.  **Output:**

    ```
    No Error Occured
    ```

    **参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ notdeepequal _ actual _ expected _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_notdeepequal_actual_expected_message)