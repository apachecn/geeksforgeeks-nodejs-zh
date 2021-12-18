# Node.js assert.ok()函数

> 原文:[https://www.geeksforgeeks.org/node-js-assert-ok-function/](https://www.geeksforgeeks.org/node-js-assert-ok-function/)

assert 模块提供了一组用于验证不变量的断言函数。 **assert.ok()** 功能测试该值是否为真。如果条件为真，则不会产生输出，否则会引发断言错误。

**语法:**

```
assert.ok(value[, message])
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **值:**此参数保存需要求值的表达式。
*   **消息:**此参数保存字符串类型的错误消息。

**返回值:**该函数返回对象类型的断言错误。

**安装 assert 模块:**

1.  You can visit the link to [Install assert module](https://www.npmjs.com/package/assert). You can install this package by using this command. 

    ```
    npm install assert
    ```

    **注意:**安装是可选步骤，因为它内置了 Node.js 模块。

2.  安装断言模块后，您可以使用命令在命令提示符下检查您的**断言**版本。

    ```
    npm version assert
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js，如下所示。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.ok(false, "It's false");
} catch(error) {
    console.log("Error: ", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 **index.js** 文件:

    ```
    node index.js
    ```

3.  **输出:**

    > 错误:AssertionError[ERR _ ASSIGNATE]:在目标处为假
    > 。(C:\用户\联想\下载\索引。js:6:12)
    > at 模块._ 编译（内部/模块/cjs/loader.js:1138:30)
    > 在对象。模块。_ 扩展..js(内部/模块/cjs/加载器。js:1158:10)
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
    assert.ok(typeof 12345 === 'number');
    console.log("No error Occured")
} catch(error) {
    console.log("Error: ", error)
}

// Function call
try {
    assert.ok(typeof 12456 === 'string');
} catch(error) {
    console.log("Error Occured: ", error)
}
```

**运行程序的步骤:**

1.  项目结构会是这样的:![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令运行 **index.js** 文件:

    ```
    node index.js
    ```

3.  **输出:**

    > 未发生错误
    > 发生错误:AssertionError[ERR _ ASSIGNATE]:表达式被评估为错误值:
    > 
    > 断言。ok(类型为 12456 = = ' string ')
    > 
    > 在对象(C:\ user \ Lenovo \ Downloads \ index。js:14:12)
    > 在模块。_ 在对象.模块. _ 扩展处编译（内部/模块/cjs/loader.js:1138:30)
    > ..js(内部/模块/cjs/加载器。js:1158:10)
    > at 模块。加载(内部/模块/cjs/加载器。js:986:32)
    > at 功能。模块。_ 加载(内部/模块/cjs/加载器。js:879:14)
    > at 功能。executeuserentrypoint[as RunMain](内部/模块/run _ main。js:71:12)
    > 在内部/主/run _ main _ main

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ ok _ value _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_ok_value_message)