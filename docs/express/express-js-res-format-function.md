# Express.js | res.format()函数

> 原文:[https://www . geesforgeks . org/express-js-RES-format-function/](https://www.geeksforgeeks.org/express-js-res-format-function/)

**res.format()** 函数对请求对象上的接受 HTTP 头(如果存在)执行*内容协商*。该函数检查接受 HTTP 请求头，然后根据接受值调用相应的处理程序。

**语法:**

```
res.format(object)
```

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

**文件名:index.js**

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function(req, res){
    res.format({
        html: function () {
          res.send('<p>Greetings from GeeksforGeeks</p>');
        },
        text: function () {
          res.send('Greetings from GeeksforGeeks');
        },      
        json: function () {
          res.send({ message: 'Greetings from GeeksforGeeks' });
        }
    });
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

在上面的例子中，当接受头字段设置为“应用/json”时，输出将是{“message”:“来自 GeeksforGeeks 的问候”}，如果接受头字段设置为“text/plain”，我们将得到“来自 GeeksforGeeks 的问候”消息作为响应。

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

4.  打开浏览器，转到 *http://localhost:3000/* ，现在你可以在屏幕上看到以下输出。

    ```
    Greetings from GeeksforGeeks
    ```