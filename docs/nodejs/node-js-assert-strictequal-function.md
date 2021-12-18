# Node.js assert.strictEqual()函数

> 原文:[https://www . geesforgeks . org/node-js-assert-strict equal-function/](https://www.geeksforgeeks.org/node-js-assert-strictequal-function/)

assert 模块提供了一组用于验证不变量的断言函数。 **assert.strictEqual()** 函数测试实际参数和预期参数之间的严格相等性。如果条件为真，则不会产生输出，否则会引发断言错误。

**语法:**

```js
assert.strictEqual(actual, expected[, message])
```

**参数:**该功能接受如下参数，如上所述，如下所述:

*   **实际:**此参数保存需要评估的实际值。它是任何类型的。
*   **预期:**此参数保存与实际值匹配的预期值。它是任何类型的。
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

var a = "GeeksforGeeks";
var b = "Geeks4Geek";

// Function call
try {
    assert.strictEqual(a, b);
} catch(error) {
    console.log("Error: ", error)
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

    > 错误:AssertionError [ERR_ASSERTION]:期望值严格相等:
    > +实际值–期望值
    > 
    > +' geeks forgeks '
    > –' geeks 4 geek '
    > ^
    > 在物体上。(C:\ user \ Lenovo \ Downloads \ index . js:4:12)
    > at Module。_ 编译(内部/模块/cjs/loader.js:1138:30)
    > 在对象.模块. _ 扩展..js(internal/modules/cjs/loader . js:1158:10)
    > at module . load(internal/modules/cjs/loader . js:986:32)
    > at function . module . _ load(internal/modules/cjs/loader . js:879:14)
    > at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
    > at internal/main/run _ main

**示例 2:**
**文件名:index.js**

```js
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.strictEqual(5, 5);
    console.log("No Error Occured");
} catch(error) {
    console.log("Error: ", error)
}

// Function call
try {
    assert.strictEqual(2, 5, new 
      TypeError('Inputs are not same'));
} catch(error) {
    console.log("Error Occured: ", error)
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

    > 未发生错误
    > 发生错误:类型错误:对象处的输入不相同
    > 。(C:\ user \ Lenovo \ Downloads \ index . js:14:30)
    > at Module。_ 在 Object.Module._extensions 处编译(内部/模块/cjs/loader.js:1138:30)
    > ..js(internal/modules/cjs/loader . js:1158:10)
    > at module . load(internal/modules/cjs/loader . js:986:32)
    > at function . module . _ load(internal/modules/cjs/loader . js:879:14)
    > at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
    > at internal/main/run _ main _ main

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ strict equal _ actual _ expected _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_strictequal_actual_expected_message)