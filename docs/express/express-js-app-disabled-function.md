# Express.js | app.disabled()功能

> 原文:[https://www . geesforgeks . org/express-js-app-disabled-function/](https://www.geeksforgeeks.org/express-js-app-disabled-function/)

**app.disabled()** 功能用于返回设置*名称*的布尔值。如果设置名称被禁用，则返回 true 如果设置名称未被禁用，则返回 false。

**语法:**

```
app.disabled(name)
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

console.log(app.disabled('trust proxy')) // true

app.enable('trust proxy')

console.log(app.disabled('trust proxy')) // false 
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
    true
    false

    ```