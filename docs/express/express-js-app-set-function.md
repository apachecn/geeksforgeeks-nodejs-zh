# Express.js | app.set()功能

> 原文:[https://www.geeksforgeeks.org/express-js-app-set-function/](https://www.geeksforgeeks.org/express-js-app-set-function/)

**app.set()功能**用于将设置名称赋值。您可以存储任何您想要的值，但是某些名称可以用来配置服务器的行为。

**语法:**

```
app.set(name, value)
```

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```
    npm install express
    ```

2.  安装 express 模块后，您可以使用命令在命令提示符下检查您的 express 版本。

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

app.set('title', 'GeeksforGeeks');

app.get('/', (req, res) => {
  res.send(app.get('title'));
})

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

4.  现在打开浏览器，转到 *http://localhost:3000/* ，会得到如下输出:

    ```
    GeeksforGeeks
    ```

这就是如何使用 express **app.set()** 函数，该函数为值分配设置名称。