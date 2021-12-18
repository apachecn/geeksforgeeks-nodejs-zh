# Express.js req.baseUrl 属性

> 原文:[https://www . geesforgeks . org/express-js-req-base URL-property/](https://www.geeksforgeeks.org/express-js-req-baseurl-property/)

**req.baseUrl** 属性是安装路由器实例的 Url 路径。req.baseUrl 属性类似于 app 对象的装载路径属性，只是 app.mountpath 返回匹配的路径模式。

**语法:**

```js
req.baseUrl
```

**参数:**无参数。

**返回:**字符串

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

var user = express.Router();

user.get('/login', function (req, res) {
  console.log(req.baseUrl);
  res.end();
})

app.use('/user', user);

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

4.  现在打开浏览器，转到**http://localhost:3000/user/log in**，现在你可以在控制台上看到如下输出:

    ```js
    Server listening on PORT 3000
    /user

    ```

**示例 2:**
**文件名:index.js**

```js
var express = require('express');
const e = require('express');
var app = express(); 
var PORT = 3000;

var student = express.Router();
app.use('/student', student);

student.get('/signup', function (req, res) {
    if(req.baseUrl == '/student')
    {
        console.log("Show Singup Form");
        res.end();
    } else {
        console.log("Invalid Request")
        res.send("Invalid Route")
    } 
})

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**现在打开浏览器，向**http://localhost:3000/学生/注册**进行 GET 请求，现在可以在控制台上看到如下输出:

```js
Show Singup Form

```

**参考:**[https://expressjs . com/en/4x/API . html # req . base URL](https://expressjs.com/en/4x/api.html#req.baseUrl)