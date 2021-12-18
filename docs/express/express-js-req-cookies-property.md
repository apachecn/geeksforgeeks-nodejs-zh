# Express.js req.cookies 属性

> 原文:[https://www . geesforgeks . org/express-js-req-cookies-property/](https://www.geeksforgeeks.org/express-js-req-cookies-property/)

当用户使用 cookie 解析器中间件时，使用 **req.cookies** 属性。此属性是一个包含请求发送的 cookies 的对象。

**语法:**

```js
req.cookies
```

**参数:**无参数。

**返回值:**对象

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
var cookieParser = require('cookie-parser');
var express = require('express');
var app = express(); 
var PORT = 3000;

app.use(cookieParser());

app.get('/', function (req, res) {
  req.cookies.title='GeeksforGeeks';  
  console.log(req.cookies);
  res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令确保您已经安装了 **express** 和 **cookie 解析器**模块:

    ```js
    npm install express
    npm install cookie-parser

    ```

3.  Run index.js file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    Server listening on PORT 3000

    ```

4.  现在打开浏览器，转到 **http://localhost:3000/** ，现在你可以在控制台上看到如下输出:

    ```js
    Server listening on PORT 3000
    [Object: null prototype] { title: 'GeeksforGeeks' }

    ```

**示例 2:** **文件名:index.js**

```js
var cookieParser = require('cookie-parser');
var express = require('express');
var app = express(); 
var PORT = 3000;

app.use(cookieParser());

app.get('/user', function (req, res) {
  req.cookies.name='Gourav';
  req.cookies.age=12;  

  console.log(req.cookies);
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

**输出:**现在打开浏览器，向**http://localhost:3000/user**发出 GET 请求，现在可以在控制台上看到如下输出:

```js
Server listening on PORT 3000
[Object: null prototype] { name: 'Gourav', age: 12 }

```

**参考:**[https://expressjs . com/en/4x/API . html # req . cookies](https://expressjs.com/en/4x/api.html#req.cookies)