# Express.js | res.clearCookie()函数

> 原文:[https://www . geesforgeks . org/express-js-RES-clear cookie-function/](https://www.geeksforgeeks.org/express-js-res-clearcookie-function/)

**res.clearCookie()** 函数用于清除名称指定的 Cookie。这个函数被调用来清除已经设置好的 cookies。例如，如果设置了*用户* cookie，则可以使用该功能将其清除。

**语法:**

```js
res.clearCookie(name, [ options ])
```

**参数:**

1.  **名称:**是要清除的 cookie 的名称。就像在下面的例子中，我们已经清除了*标题* cookie。
2.  **选项:**是可以有域、编码、路径、安全等各种属性的对象。

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

**文件名:index.js**

```js
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function(req, res){

    // Setting cookie (key-value)
    res.cookie('title', 'geeksforgeeks');

    // Clearing the cookie
    res.clearCookie('title');

    console.log("Cookie cleared");
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

4.  现在打开浏览器，进入 *http://localhost:3000/* ，在屏幕上可以看到如下输出:

    ```js
    Server listening on PORT 3000
    Cookie cleared

    ```