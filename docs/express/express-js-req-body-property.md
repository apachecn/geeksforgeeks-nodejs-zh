# Express.js req.body 属性

> 原文:[https://www.geeksforgeeks.org/express-js-req-body-property/](https://www.geeksforgeeks.org/express-js-req-body-property/)

**req.body** 属性包含在请求正文中提交的数据的键值对。默认情况下，它是未定义的，当您使用名为 body-parsing 的中间件(如 express.urlencoded()或 express.json()。

**语法:**

```
req.body
```

**参数:**无参数。

**返回值:**对象

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
var app = express(); 
var PORT = 3000;

// For parsing application/json
app.use(express.json());

// For parsing application/x-www-form-urlencoded
app.use(express.urlencoded({ extended: true }));

app.post('/profile', function (req, res) {
  console.log(req.body);
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

4.  Now make POST request to **http://localhost:3000/profile** with following body:

    ```
     {
         "title":"Greetings from GeeksforGeeks"
     }

    ```

    现在，您可以在控制台上看到以下输出:

    ```
    Server listening on PORT 3000
    { title: 'Greetings from GeeksforGeeks' }

    ```

**示例 2:** **文件名:index.js**

```
var express = require('express');
var app = express(); 
var PORT = 3000;

app.use(express.json());
app.use(express.urlencoded({ extended: true }));

app.post('/signup', function (req, res) {
  var data = req.body;

  console.log("Name: ", data.name);
  console.log("Age: ", data.age);
  console.log("Gender: ", data.gender);

  res.send();
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

现在向**http://localhost:3000/注册**发出 POST 请求，请求正文如下:

```
 {
     "name": "Gourav",
     "age": 13,
     "gender":"Male"
 }

```

**输出:**现在您将在控制台屏幕上看到以下输出:

```
Server listening on PORT 3000
Name:  Gourav
Age:  13
Gender:  Male

```

**参考:**[https://expressjs . com/en/4x/API . html # req . body](https://expressjs.com/en/4x/api.html#req.body)