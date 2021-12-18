# Express.js res.status()函数

> 原文:[https://www . geesforgeks . org/express-js-RES-status-function/](https://www.geeksforgeeks.org/express-js-res-status-function/)

**res.status()** 功能设置响应的 HTTP 状态。它是节点响应的可链接别名

**语法:**

```js
res.status( code )
```

**参数:**该功能接受保存 HTTP 状态码的单参数**码**。

**返回:**返回一个对象。

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

**示例 1:**
**文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

// Without middleware
app.get('/user', function(req, res){
    res.status(200).send("User Page");
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

4.  现在打开浏览器，转到*http://localhost:3000/user*，在你的屏幕上，你会看到如下输出:

    ```js
    User Page
    ```

**示例 2:**
**文件名:index.js**

```js
var express = require('express');
const path = require('path');
var app = express();
var PORT = 3000;

//with middleware
app.use('/', function(req, res, next){
    res.status(200).send("Status Working");
   next();
});

app.get('/', function(req, res){
    console.log("Home Page!")
    res.send();
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

现在打开浏览器，转到 *http://localhost:3000/* ，现在检查你的控制台，你会看到如下输出:

```js
Server listening on PORT 3000
Home Page!

```

您将在浏览器屏幕上看到以下输出:

```js
Status Working
```

**参考:**[https://expressjs . com/en/5x/API . html # RES . status](https://expressjs.com/en/5x/api.html#res.status)