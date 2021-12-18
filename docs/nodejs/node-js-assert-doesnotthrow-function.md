# node . js assert . do notthrow()函数

> 原文:[https://www . geesforgeks . org/node-js-assert-dosnotthrow-function/](https://www.geeksforgeeks.org/node-js-assert-doesnotthrow-function/)

assert 模块提供了一组用于验证不变量的断言函数。**assert . do notthrow()**函数断言函数 fn 不会抛出错误。

**语法:**

```js
assert.doesNotThrow(fn[, error][, message])
```

**参数:**该功能接受如下参数，如上所述，如下所述:

*   **fn:** 这个参数是一个不会抛出错误的函数。
*   **错误:**此参数是正则表达式或函数。这是指定的错误。这是一个可选参数。
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
    assert.doesNotThrow(
        () => {
          throw new TypeError('Wrong value');
        },
    );
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

    > 错误:断言错误[ERR _ ASSIGNAL]:获得了不需要的异常。
    > 实际消息:“对象上的错误值”
    > 。<anonymous>(C:\ Users \ Lenovo \ Downloads \ index . js:6:12)
    > at Module。_ 编译(内部/模块/cjs/loader.js:1138:30)
    > 在对象.模块. _ 扩展..js(internal/modules/cjs/loader . js:1158:10)
    > at module . load(internal/modules/cjs/loader . js:986:32)
    > at function . module . _ load(internal/modules/cjs/loader . js:879:14)
    > at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
    > at internal/main/run _ main<anonymous>(C:\ Users \ NEW \ Assert Function \ index . js:6:12)
    > at Module。_ 编译(内部/模块/cjs/loader . js:1138:30)
    > at object . module . _ extensions..js(internal/modules/cjs/loader . js:1158:10)
    > at module . load(internal/modules/cjs/loader . js:986:32)
    > at function . module . _ load(internal/modules/cjs/loader . js:879:14)
    > at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
    > at internal/main/run</anonymous></anonymous>

**示例 2:** **文件名:index.js**

```js
// Requiring the module
const assert = require('assert').strict;

// Function call
try {
    assert.doesNotThrow(
        () => {
          throw new TypeError('The Wrong value error');
        },
        /abcd/,
        'Whoops'
    );
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

    > 错误:类型错误:C:\ user \ Lenovo \ Downloads \ geesforgeeks 实习\ NEW \ Assert \ index . js:8:17
    > at getActual(Assert . js:657:5)
    > at function . doesnotthrow(Assert . js:805:32)
    > at Object。<anonymous>(C:\实习\ NEW \ Assert Function \ index . js:6:12)
    > 在模块。_ 在 Object.Module._extensions 处编译(内部/模块/cjs/loader.js:1138:30)
    > ..js(internal/modules/cjs/loader . js:1158:10)
    > at module . load(internal/modules/cjs/loader . js:986:32)
    > at function . module . _ load(internal/modules/cjs/loader . js:879:14)
    > at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
    > at internal/main/run</anonymous>

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ dosnotthrow _ fn _ error _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_doesnotthrow_fn_error_message)