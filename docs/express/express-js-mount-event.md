# Express.js 挂载事件

> 原文:[https://www.geeksforgeeks.org/express-js-mount-event/](https://www.geeksforgeeks.org/express-js-mount-event/)

**mount** 事件在子应用上挂载到父应用时被激发，父应用基本上被传递给回调函数。

**语法:**

```
app.on('mount', callback(parent))
```

**参数:**是一个名为‘mount’的事件，调用该事件时会调用回调函数。

**返回值:**因为是事件所以没有任何返回值。

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
var app = express();  // The main app
var admin = express();
var PORT = 3000;

admin.on('mount', function (parent) {
  console.log('Admin Mounted');
});

admin.get('/', function (req, res) {
  res.send('Admin Homepage');
});

app.use('/admin', admin);

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
    Admin Mounted
    Server listening on PORT 3000

    ```

4.  现在打开浏览器，进入*http://localhost:3000/admin*，现在你可以在屏幕上看到如下输出:

    ```
    Admin Homepage
    ```

**示例 2:**
**文件名:index.js**

```
var express = require('express');
var app = express();  // The main app
var student = express();
var teacher = express();
var PORT = 3000;

// Multiple mounting
teacher.on('mount', function (parent) {
    console.log('Teacher Mounted');
});

student.on('mount', function (parent) {
  console.log('Student Mounted');
});

app.use('/student', student);
app.use('/teacher', teacher);

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
Student Mounted
Teacher Mounted
Server listening on PORT 3000

```

**参考:**[https://expressjs . com/en/4x/API . html # app . on count](https://expressjs.com/en/4x/api.html#app.onmount)