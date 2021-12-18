# Express.js router.all()功能

> 原文:[https://www . geesforgeks . org/express-js-router-all-function/](https://www.geeksforgeeks.org/express-js-router-all-function/)

**路由器. all()** 功能和路由器一样。METHOD()方法，除了它匹配所有 HTTP 方法(动词)。这对于映射任意匹配或特定路径前缀的*全局*逻辑非常有帮助。

**语法:**

```js
router.all(path, [callback, ...] callback)
```

**参数:**路径参数是指定 URL 的路径，回调是作为参数传递的函数。

**返回值:**返回响应。

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
var router = express.Router();
var PORT = 3000;

// Setting single route  
router.all('/user', function (req, res) {
    console.log("User Page Called");
    res.end();
});

app.use(router);

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

4.  Now make any request to *http://localhost:3000/user* like POST, PUT, DELETE or any other type of request, it will shown the following output

    ```js
    User Page Called    

    ```

    对*http://localhost:3000/user*的每一种请求都会打印出相同的输出。

**示例 2:** **文件名:index.js**

```js
var express = require('express');
var app = express();
var router = express.Router();
var PORT = 3000;

// Setting multiple routes  
router.all('/user', function (req, res) {
    console.log("User Page Called");
    res.end();
});

router.all('/student', function (req, res) {
    console.log("Student Page Called");
    res.end();
});

router.all('/teacher', function (req, res) {
    console.log("Teacher Page Called");
    res.end();
});

app.use(router);

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

现在向*http://localhost:3000/用户*、*http://localhost:3000/学生*和*http://localhost:3000/老师*发出 GET 请求，会显示如下输出。

```js
User Page Called 
Student Page Called 
Teacher Page Called    

```

**参考:**[https://expressjs . com/en/4x/API . html # router . all](https://expressjs.com/en/4x/api.html#router.all)