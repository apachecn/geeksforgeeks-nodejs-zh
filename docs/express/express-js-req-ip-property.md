# Express.js req.ip 属性

> 原文:[https://www.geeksforgeeks.org/express-js-req-ip-property/](https://www.geeksforgeeks.org/express-js-req-ip-property/)

**req.ip** 属性包含请求的远程 ip 地址。当用户想要向应用程序发出的传入请求的 IP 地址时，它非常有用。

**语法:**

```
req.ip
```

**参数:**无参数。

**返回值:**字符串

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
  console.log(req.ip);
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

4.  现在打开浏览器，转到 **http://localhost:3000/** ，现在你可以在控制台上看到如下输出:

    ```
    Server listening on PORT 3000
    ::1

    ```

**示例 2:** **文件名:app.js**

```
var express = require('express');
var app = express(); 
var PORT = 3000;

app.enable('trust proxy')
app.get('/', function (req, res) {
  console.log(req.ip);
  res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

使用以下命令运行 **app.js** 文件:

```
node app.js
```

**输出:**

```
Server listening on PORT 3000

```

现在打开浏览器，向 **http://localhost:3000/** 发出 GET 请求，头部设置为**x-forward-for:203.0.113.195**，现在您可以在控制台上看到以下输出:

```
Server listening on PORT 3000
203.0.113.195

```

**参考:**[https://expressjs . com/en/4x/API . html # req . IP](https://expressjs.com/en/4x/api.html#req.ip)