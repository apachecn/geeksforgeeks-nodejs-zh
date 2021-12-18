# Express.js app.engine()功能

> 原文:[https://www . geesforgeks . org/express-js-app-engine-function/](https://www.geeksforgeeks.org/express-js-app-engine-function/)

**app.engine()** 函数用于将给定的模板引擎回调注册为 ext。默认情况下，Express 本身将需要()基于文件扩展名的引擎。

**语法:**

```js
app.engine(ext, callback)
```

**参数:**ext 参数是像 ejs、hbs 等这样的扩展类型，callback 是作为参数传递的函数。

**返回值:**返回对象。

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

4.  Create a views folder and put **home.html** file in it with the following code:

    **示例 1:**
    **文件名:home.html**

    ```js
    <html>
    <head>
      <title>app.engine() Demo</title>
    </head>
    <body>
        <h2>EJS Engine</h2>
    </body>
    </html>
    ```

例如，将 EJS 模板引擎映射到”。html "文件:

```js
app.engine('html', require('ejs').renderFile);
```

**文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

app.engine('html', require('ejs').renderFile);

app.get('/', function (req, res) {
    res.render("home.html")
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

1.  使用以下命令确保您已经安装了 **express** 和 **ejs** 模块:

    ```js
    npm install express
    npm install ejs

    ```

2.  Run index.js file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    Server listening on PORT 3000

    ```

3.  现在打开浏览器，转到 **http://localhost:3000/** ，在浏览器上可以看到如下输出:

    ```js
    EJS Engine

    ```

**示例 2:** **文件名:home.html**

```js
<html>
<head>
  <title>app.engine() Demo</title>
</head>
<body>
    <h2>Handlebars Engine</h2>
</body>
</html>
```

**文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

console.log(app.engine('html', require('hbs').renderFile));

app.get('/', function (req, res) {
    res.render("home.html")
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

1.  使用以下命令确保您已经安装了 **express** 和 **hbs** 模块:

    ```js
    npm install express
    npm install hbs

    ```

2.  Run index.js file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    Server listening on PORT 3000

    ```

3.  现在打开浏览器，转到 **http://localhost:3000/** ，在浏览器上可以看到如下输出:

    ```js
    Handlebars Engine

    ```

**参考:**T2】https://expressjs.com/en/4x/api.html#app.engine