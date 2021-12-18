# 节点 js 导出模块

> 原文:[https://www.geeksforgeeks.org/node-js-export-module/](https://www.geeksforgeeks.org/node-js-export-module/)

Node.js 中的**模块. export**用于将任何文字、函数或对象作为一个模块导出。它用于将 JavaScript 文件包含到 node.js 应用程序中。**模块**类似于用于表示当前模块的变量，**导出**是作为模块公开的对象。

**语法:**

*   ```js
    module.exports = literal | function | object
    ```

    **说明:**这里赋值(字面|函数|对象)直接作为模块公开，可以直接使用。

*   ```js
    module.exports.variable = literal | function | object
    ```

    **说明:**这里赋值(字面|函数|对象)是作为模块间接公开的，可以使用变量来消耗。

**示例 1:** 导出文字

*   Create a file named **app.js** and use `module.exports` to export the text.

    ```js
    module.exports = "GeeksforGeeks";
    ```

*   Create a file named **index.js** , and import the file app.js to print the exported text to the console.

    ```js
    const company = require("./app");
    console.log(company);
    ```

*   **Output:**

    ```js
    GeeksforGeeks
    ```

**示例 2:** 导出对象

*   Create a file named **app.js** and use `module.exports` to export the object.

    ```js
    module.exports = {
      name: 'GeeksforGeeks',
      website: 'https://geeksforgeeks.org'
    }
    ```

*   Create a file named **index.js** , and import the file app.js to print the exported object data to the console.

    ```js
    const company = require('./app');

    console.log(company.name);
    console.log(company.website);
    ```

*   **Output:**

    ```js
    GeeksforGeeks
    https://geeksforgeeks.org

    ```

**示例 3:** 导出功能

*   创建一个名为 **app.js** 的文件，并使用`module.exports`导出该函数。

    ```js
    module.exports = function (a, b) {
      console.log(a + b);
    }
    ```

*   创建一个名为 **index.js** 的文件，导入文件 app.js 使用导出的功能。

    ```js
    const sum = require('./app');

    sum(2, 5);
    ```

*   **输出:**

    ```js
    7
    ```

**示例 4:** 将函数导出为类

*   Create a file named **app.js** . Use this keyword to define the function, and use `module.exports` to export the function.

    ```js
    module.exports = function () {
      this.name = 'GeeksforGeeks';
      this.website = 'https://geeksforgeeks.org';
      this.info = () => {
        console.log(`Company name - ${this.name}`);
        console.log(`Website - ${this.website}`);
      }
    }
    ```

*   Create a file named **index.js** , import the file app.js and use the exported function as a class.

    ```js
    const Company = require('./app');

    const firstCompany = new Company();

    firstCompany.info();
    ```

*   **Output:**

    ```js
    Company name - GeeksforGeeks
    Website - https://geeksforgeeks.org

    ```

**示例 5:** 从单独的文件夹

```js
const index = require('./models/lang/index.js');
```

加载模块

**说明:**在上面的例子中，index.js 文件位于 models 文件夹内的 lang 文件夹下。我们可以使用`./`转到根文件夹，然后相对于它移动。