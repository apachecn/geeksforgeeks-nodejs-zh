# Express.js | app.all()功能

> 原文:[https://www.geeksforgeeks.org/express-js-app-all-function/](https://www.geeksforgeeks.org/express-js-app-all-function/)

**app.all()** 功能用于路由所有类型的 HTTP 请求。例如，如果我们有 POST、GET、PUT、DELETE 等，对任何特定路由的请求，比如说*/用户*，那么我们可以定义单个 API**app . all(/用户)**，它将接受所有类型的 HTTP 请求，而不是定义不同的 API，比如 app . POST(“/用户”)、app . GET(“/用户”)等。

**语法:**

```
app.all( path, callback )
```

**参数:**

1.  **路径:**是调用中间件函数的路径。
2.  **回调:**可以是中间件功能，也可以是一系列/数组功能。

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
var PORT = 3000;

app.all('/user', function (req, res, next) {
    console.log('USER API CALLED');
    next(); 
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
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
    Server listening on PORT 3000

    ```

4.  现在打开浏览器，对*HTTP://localhost:3000/user*进行 GET、POST、PUT、DELETE 或任何其他 HTTP 请求方法，您将在控制台上看到以下输出:

    ```
    Server listening on PORT 3000
    USER API CALLED

    ```