# express . js RES . header sent Property

> 原文:[https://www . geesforgeks . org/express-js-RES-header sent-property/](https://www.geeksforgeeks.org/express-js-res-headerssent-property/)

**RES . header sent**属性是一个布尔属性，指示应用程序是否为响应发送了 HTTP 头。

**语法:**

```
res.headersSent
```

**参数:**无参数。

**返回值:**该属性返回真或假的布尔值。

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

app.get('/', function (req, res) {

    // Before res.send() 
    console.log(res.headersSent); 
    res.send('OK');
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

4.  现在打开浏览器，转到 *http://localhost:3000/* ，现在你可以在控制台上看到如下输出:

    ```
    Server listening on PORT 3000
    false

    ```

**示例 2:** **文件名:index.js**

```
var express = require('express');
var app = express(); 
var PORT = 3000;

app.get('/', function (req, res) {
    res.send('OK');

    // After res.send() 
    console.log(res.headersSent); 
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

**输出:**
现在打开浏览器，向 **http://localhost:3000** 发出 GET 请求，现在可以在控制台上看到如下输出:

```
Server listening on PORT 3000
true

```

**参考:**[https://expressjs . com/en/4x/API . html # RES . header sen](https://expressjs.com/en/4x/api.html#res.headersSent)