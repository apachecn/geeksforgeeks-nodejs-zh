# Express.js res.redirect()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-redirect-function/](https://www.geeksforgeeks.org/express-js-res-redirect-function/)

**res.redirect()** 函数将一个对应于 HTTP 状态代码的整数(正数)重定向到从指定路径派生的具有指定状态的 URL。默认状态为“找到 302”。

**语法:**

```js
res.redirect([status, ] path)
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **状态:**此参数保存 HTTP 状态代码
*   **路径:**此参数描述路径。

**返回值:**返回一个对象。

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```js
    npm install express
    ```

2.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

    ```js
    npm version express
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

    ```js
    node index.js
    ```

**示例 1:** **文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

// Without middleware
app.get('/', function(req, res){
    res.redirect('/user');
});

app.get('/user', function(req, res){
    res.send("Redirected to User Page");
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

4.  现在打开浏览器，进入 *http://localhost:3000/* ，现在在你的屏幕上你会看到如下输出:

    ```js
    Redirected to User Page
    ```

**示例 2:** **文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

// With middleware
app.use('/verify', function(req, res, next){
    console.log("Authenticate and Redirect")
    res.redirect('/user');
    next();
});

app.get('/user', function(req, res){
    res.send("User Page");
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

现在打开浏览器，转到*http://localhost:3000/验证*，现在检查你的控制台，你会看到如下输出:

```js
Server listening on PORT 3000
Authenticate and Redirect

```

您将在浏览器上看到以下输出:

```js
User Page

```

**参考:**[https://expressjs . com/en/5x/API . html # RES .重定向](https://expressjs.com/en/5x/api.html#res.redirect)