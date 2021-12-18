# express . js req . fresh Property

> 原文:[https://www . geesforgeks . org/express-js-req-fresh-property/](https://www.geeksforgeeks.org/express-js-req-fresh-property/)

如果客户端缓存中的响应仍然是“新鲜的”，则 **req.fresh** 属性返回 true，否则将返回 false。

**语法:**

```js
req.fresh
```

**参数:**无参数

**返回值:**真或假

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
  console.log(req.fresh);
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
    false

    ```

**示例 2:** 考虑上面的代码，但是这次，在 Header 设置为 **Cache-Control: no-cache** 的情况下，向 **http://localhost:3000/** 发出 GET 请求，现在您可以在控制台上看到以下输出:

```js
Server listening on PORT 3000
false

```

**参考资料:**[https://expressjs . com/en/4x/API . html # req . fresh](https://expressjs.com/en/4x/api.html#req.fresh)