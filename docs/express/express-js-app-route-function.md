# Express.js | app.route()功能

> 原文:[https://www . geesforgeks . org/express-js-app-route-function/](https://www.geeksforgeeks.org/express-js-app-route-function/)

**app.route()函数**返回单个路由的一个实例，然后您可以使用它来处理带有可选中间件的 HTTP 动词。使用 app.route()避免重复的路由名称(从而避免输入错误)。

**语法:**

```js
app.route( path )
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
var PORT = 3000;

app.route('/user')
.get((req, res, next) => {
    res.send('GET request called');
})
.post((req, res, next) => {
res.send('POST request called');
})
.all((req, res, next) => {
res.send('Other requests called');
})

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
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
    Server listening on PORT 3000

    ```

4.  现在，如果我向*/用户*发出 POST 请求，我们会得到名为的 **POST 请求，同样，如果我向*/用户*发出 get 请求，我们会得到名为**的 **GET 请求，以此类推。**

这就是如何使用 express **app.route()** 函数的方法，该函数返回单个路由的实例，然后您可以使用可选的中间件来处理 HTTP 动词。