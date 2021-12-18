# Express.js | app.get()功能

> 原文:[https://www.geeksforgeeks.org/express-js-app-get-function/](https://www.geeksforgeeks.org/express-js-app-get-function/)

**app.get()** 函数返回值*名称* app 设置。 **app.set()** 功能用于将设置名称赋值。这个函数用于获取被赋值的值。

**语法:**

```
app.get(name)
```

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```
    npm install express
    ```

2.  安装 express 模块后，您可以使用命令在命令提示符下检查您的 express 版本。

    ```
    npm version express
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

    ```
    node index.js
    ```

**文件名:index.js**

```
var express = require('express');
var app = express();

console.log(app.get('title')) // undefined

app.set('title', 'GeeksforGeeks')

console.log(app.get('title')) // GeeksforGeeks
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令确保您已经安装了 **express** 模块:

    ```
    npm install express
    ```

3.  Run index.js file using below command:

    ```
    node index.js
    ```

    **输出:**

    ```
    undefined
    GeeksforGeeks

    ```