# Express.js | app.enable()功能

> 原文:[https://www . geesforgeks . org/express-js-app-enable-function/](https://www.geeksforgeeks.org/express-js-app-enable-function/)

**app.enable()** 功能用于将布尔值即名称设置为真。它基本上是 app.set(name，true)或 app.set(name，false)的简写。因此，我们可以使用 **app.enable(名称)**函数将布尔值设置为某些系统 Express.js 设置。

**语法:**

```js
app.enable(name)
```

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```js
    npm install express
    ```

2.  安装 express 模块后，您可以使用命令在命令提示符下检查您的 express 版本。

    ```js
    npm version express
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

    ```js
    node index.js
    ```

**文件名:index.js**

```js
var express = require('express');
var app = express();

app.enable('trust proxy')

console.log(app.get('trust proxy')) // true
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令确保您已经安装了 **express** 模块:

    ```js
    npm install express
    ```

3.  Run index.js file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    true

    ```