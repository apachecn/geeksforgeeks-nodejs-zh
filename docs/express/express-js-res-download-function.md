# Express.js res.download()功能

> 原文:[https://www . geesforgeks . org/express-js-RES-download-function/](https://www.geeksforgeeks.org/express-js-res-download-function/)

**res.download()** 函数将路径中的文件作为“附件”传输。通常，浏览器会提示用户下载。

**语法:**

```
res.download(path [, filename] [, options] [, fn])
```

**参数:**文件名是要作为附件下载的文件的名称，fn 是一个回调函数。

**返回值:**不返回任何东西。

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

app.get('/', function(req, res){
    res.download('Hello.txt');
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```

将任何可以下载的文件放在项目的根目录下，就像这里我们使用的 **Hello.txt** 一样。

**运行程序的步骤:**

1.  Use the following command to make sure that you have installed the **express** module:

    ```
    npm install express
    ```

2.  使用以下命令运行 index.js 文件:

    ```
    node index.js
    ```

    **输出:**

    ```
    Server listening on PORT 3000

    ```

3.  Open the browser and go to *http://localhost: 3000/*. Now you can see the "Hello.txt" file being downloaded on the screen.

**示例 2:** **文件名:**

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function(req, res){
    res.download('Unknown_file.txt', function(error){
        console.log("Error : ", error)
    });
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

打开浏览器，转到 *http://localhost:3000/* ，在控制台上会看到如下输出:

```
Error :  [Error: ENOENT: no such file or directory, 
  stat 'C:\\Users\\Unknown_file.txt'] {
  errno: -4058,
  code: 'ENOENT',
  syscall: 'stat',
  path: 'C:\\Users\\Unknown_file.txt',
  expose: false,
  statusCode: 404,
  status: 404
}

```

**参考:**[https://expressjs . com/en/4x/API . html # RES . download](https://expressjs.com/en/4x/api.html#res.download)