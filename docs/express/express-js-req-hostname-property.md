# Express.js req.hostname 属性

> 原文:[https://www . geesforgeks . org/express-js-req-hostname-property/](https://www.geeksforgeeks.org/express-js-req-hostname-property/)

**req.hostname** 属性包含从主机 HTTP 头派生的主机名。它基本上返回主机 HTTP 头中提供的主机名。

**语法:**

```js
req.hostname
```

**参数:**无参数

**返回值:**字符串

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
var PORT = 3000;

app.get('/', function (req, res) {
  console.log(req.hostname);
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

4.  现在打开浏览器，转到 **http://localhost:3000/** ，现在你可以在控制台上看到如下输出:

    ```js
    Server listening on PORT 3000
    localhost

    ```

**例 2:** 假设我们有一个域名而不是*本地主机*，如下图:

```js
Host: "demo.com:3000"
console.log(req.hostname);

```

**输出:**

```js
demo.com
```

**参考:**[https://expressjs . com/en/4x/API . html # req . hostname](https://expressjs.com/en/4x/api.html#req.hostname)