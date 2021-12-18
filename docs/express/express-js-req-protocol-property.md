# Express.js req.protocol 属性

> 原文:[https://www . geesforgeks . org/express-js-req-protocol-property/](https://www.geeksforgeeks.org/express-js-req-protocol-property/)

**req.protocol** 属性包含请求协议字符串，该字符串可以是 HTTP，也可以是(对于 TLS 请求)https。当信任代理设置的计算结果不为假时，如果该属性存在，它将使用 X-Forwarded-Proto 头字段值。

**语法:**

```
req.protocol
```

**参数:**无参数。

**返回:**字符串。

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

**示例 1:**
**文件名:index.js**

```
var express = require('express');
var app = express(); 
var PORT = 3000;

app.get('/', function (req, res) {
  console.log(req.protocol);
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
    http

    ```

**示例 2:** 考虑上面的代码，但是假设这个项目部署在如下所示的 Https 服务器上:

```
https://www.example.com
```

现在，如果我们尝试打印 *req.protocol* 值，将会输出以下内容:

```
https
```

**参考:**T2】https://expressjs.com/en/4x/api.html#req.protocol