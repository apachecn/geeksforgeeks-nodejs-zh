# express . js req . acceptscharsets()函数

> 原文:[https://www . geesforgeks . org/express-js-req-acceptscharsets-function/](https://www.geeksforgeeks.org/express-js-req-acceptscharsets-function/)

**req.acceptsCharsets()** 函数根据请求的 Accept-Charset HTTP 头字段返回指定字符集的第一个被接受的字符集，否则如果没有指定字符集被接受，则返回 false。

**语法:**

```
req.acceptsCharsets(charset [, ...])
```

**参数:**字符集参数是像‘UTF-8’等字符集代码。

**返回值:**字符串(如果为真)或假。

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
    console.log(req.get('Accept-Charset'));    
    console.log(req.acceptsCharsets('UTF-8')); 
    res.end();
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

4.  现在向 *http://localhost:3000/* 发出 GET 请求，头部设置为**“Accept-Charset:UTF-8”**，然后您将在控制台上看到以下输出:

    ```
    Server listening on PORT 3000
    UTF-8
    UTF-8

    ```

**示例 2:** **文件名:index.js**

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {
    console.log(req.get('Accept-Charset'));    
    console.log(req.acceptsCharsets('ISO-8859-1'));
    res.end();
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

现在向 *http://localhost:3000/* 发出 GET 请求，头部设置为**“Accept-Charset:UTF-8”**，然后您将在控制台上看到以下输出:

```
Server listening on PORT 3000
UTF-8
false

```

**参考:**[https://expressjs . com/en/5x/API . html # req . accept sharsets](https://expressjs.com/en/5x/api.html#req.acceptsCharsets)