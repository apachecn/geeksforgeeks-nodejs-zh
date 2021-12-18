# Express.js | app.path()功能

> 原文:[https://www.geeksforgeeks.org/express-js-app-path-function/](https://www.geeksforgeeks.org/express-js-app-path-function/)

**app.path()函数**将应用的规范路径作为字符串返回。在复杂的已安装应用程序情况下，这种方法的行为会变得非常复杂。通常最好使用 req.baseUrl 来获取应用程序的规范路径。

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
var PORT = 3000;

var app = express()
var blog = express()
var blogAdmin = express()

app.use('/user', blog)
blog.use('/admin', blogAdmin)

console.dir(app.path()) // ''
console.dir(blog.path()) // '/blog'
console.dir(blogAdmin.path()) // '/blog/admin'
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
    ''
    '/user'      
    '/user/admin'

    ```

这就是如何使用 express **app.path()** 函数，该函数将应用程序的规范路径作为字符串返回。