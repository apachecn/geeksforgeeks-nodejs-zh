# Express.js app.mountpath 属性

> 原文:[https://www . geesforgeks . org/express-js-app-mount path-property/](https://www.geeksforgeeks.org/express-js-app-mountpath-property/)

**app.mountpath** 属性包含一个或多个路径模式，子应用安装在这些路径模式上。

**语法:**

```
app.mountpath
```

**参数:**无参数。

**返回值:**字符串。

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```
    npm install express
    ```

2.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

    ```
    npm version express
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

    ```
    node index.js
    ```

**示例 1:** **文件名:index.js**

```
var express = require('express');
var app = express();  // the main app
var user = express(); // the sub app
var PORT = 3000;

user.get('/', function (req, res) {
  console.log(user.mountpath); // /user
  res.send('User Homepage');
});

app.use('/user', user); // Mounting the sub app

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

4.  现在打开浏览器，转到*http://localhost:3000/user*，现在你可以在控制台上看到如下输出:

    ```
    Server listening on PORT 3000
    /user

    ```

**示例 2:** **文件名:index.js**

```
var express = require('express');
var app = express(); 
var PORT = 3000;

app.get('/', function (req, res) {
    console.log(app.mountpath)
    res.send("OK")
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 index.js 文件:

```
node index.js
```

**输出:**现在打开浏览器，向 **http://localhost:3000** 发出 GET 请求，现在可以在控制台上看到如下输出:

```
Server listening on PORT 3000
/

```

**参考:**[https://expressjs . com/en/4x/API . html # app . mount path](https://expressjs.com/en/4x/api.html#app.mountpath)