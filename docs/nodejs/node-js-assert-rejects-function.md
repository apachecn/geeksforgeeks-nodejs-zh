# Node.js assert.rejects()函数

> 原文:[https://www . geesforgeks . org/node-js-assert-rejects-function/](https://www.geeksforgeeks.org/node-js-assert-rejects-function/)

assert 模块提供了一组用于验证不变量的断言函数。 **assert.rejects()** 函数等待 asyncFn 承诺，或者如果 asyncFn 是一个函数，那么它立即调用该函数并等待返回的承诺完成，然后它将检查承诺是否被拒绝。

**语法:**

```js
assert.rejects(asyncFn[, error][, message])
```

**参数:**该功能接受如下参数，如上所述，如下所述:

*   **asyncFn:** 该参数是异步函数，同步抛出错误。
*   **错误:**该参数的类型可以是类、正则表达式、验证函数或每个属性将被测试的对象。这是一个可选参数。
*   **消息:**如果 asyncFn 拒绝失败，该参数将是 AssertionError 提供的消息。这是一个可选参数。

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
(async () => {
    assert.strictEqual(1,2)
    await assert.rejects(
      async () => {
        throw new TypeError('Wrong value');
      },
      (err) => {
        assert.strictEqual(err.name, 'TypeError');
        assert.strictEqual(err.message, 'Wrong value');
        return true;
      }
    ).then(() => {
        console.log("Reject Demo")
    });
})();
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  Run **index.js** file using below command:

    ```js
    node index.js
    ```

    **输出:**

    > (节点:12704)unhandledprozerejectionwarning:AssertionError[ERR _ ASSERTION]:要求
    > 值严格相等:
    > 
    > 1 ! == 2
    > 
    > at C:\ Users \ Lenovo \ Downloads \ geesforgeks 实习\index.js:25:12
    > at Object。(C:\ Users \ Lenovo \ Downloads \ geesforgeks 实习\ NEW \ Assert Function
    > \ index . js:38:3)
    > at Module。_ 在 Object.Module._extensions 处编译(内部/模块/cjs/loader.js:1138:30)
    > ..js(internal/modules/cjs/loader . js:1158:10)
    > at module . load(internal/modules/cjs/loader . js:986:32)
    > at function . module . _ load(internal/modules/cjs/loader . js:879:14)
    > at function . executeuserentrypoint[as runMain](internal/modules/run _ main . js:71:12)
    > at internal/main/run _ main _ main 这个
    > 错误要么是由于在没有 catch 块的情况下抛出异步函数内部引起的，
    > 要么是由于拒绝了一个没有处理的承诺。catch()。要在未处理的承诺拒绝时终止节点
    > 进程，请使用 CLI 标志`–未处理的拒绝=严格`
    > (请参见 https://nodejs . org/API/CLI . html # CLI _ unhandled _ rejects _ mode)。
    > (拒绝 id: 1)

**示例 2:** **文件名:index.js**

```js
// Requiring the module
 const assert = require('assert').strict;

// Function call
(async () => {
    assert.strictEqual(1,1)
    await assert.rejects(
      async () => {
        throw new TypeError('Wrong value');
      },
      (err) => {
        assert.strictEqual(err.name, 'TypeError');
        assert.strictEqual(err.message, 'Wrong value');
        return true;
      }
    ).then(() => {
        console.log("Reject Demo Works Successfully")
    });
})();
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
    Reject Demo Works Successfully

    ```

**参考:**[https://nodejs . org/dist/latest-v 12 . x/docs/API/assert . html # assert _ assert _ rejects _ async fn _ error _ message](https://nodejs.org/dist/latest-v12.x/docs/api/assert.html#assert_assert_rejects_asyncfn_error_message)