# 在 Node.js 中实现 Csurf 中间件

> 原文:[https://www . geeksforgeeks . org/impering-csurf-节点内中间件-js/](https://www.geeksforgeeks.org/implementing-csurf-middleware-in-node-js/)

Node.js 中的 Csurf 模块防止对应用程序的跨站点请求伪造(CSRF)攻击。通过使用这个模块，当浏览器从服务器呈现一个页面时，它会发送一个随机生成的字符串作为 **CSRF** 标记。因此，当执行开机自检请求时，它将随机发送 CSRF 令牌作为 cookie。对于每个请求，发送的令牌都是不同的，因为它们是随机生成的。
**先决条件**

*   您选择的集成开发环境
*   node.js 和 npm 在您的系统中安装和设置
*   Node.js 模块和嵌入式 JavaScript(ejs)的基本知识。

**安装:**

1.  首先，我们需要用 **package.json** 文件初始化我们的应用程序。因此，在终端中写下以下命令:

```
npm init
```

2.  之后， **package.json** 被创建，是时候安装我们的依赖了。因此，通过以下命令安装所需的依赖项:

```
npm install body-parser cookie-parser express csurf --save
```

1.  **Cookie 解析器**用于解析传入的 Cookie。**正文解析器**用于解析我们将在一个 HTML 文件中创建的输入表单数据。

2.  创建一个名为 **app.js** 的文件，并为需求模块编写如下代码:
    **文件名:app.js**

## java 描述语言

```
const express = require('express');
const csrf = require('csurf');
const cookieParser = require('cookie-parser');
const bodyParser = require('body-parser');
```

1.  这里， **csrf** 将作为生成和验证 CSRF cookie 的中间件。这个中间件将增加一个生成 cookies 的功能。该函数将通过隐藏的表单字段传递给请求。当用户发送请求时，这个创建的 cookie 将被验证。中间件填充 **req.csrfToken()** 。

2.  现在我们已经要求了所有的模块，现在让我们写下完整的代码如下所示:
    **文件名:app.js**

## java 描述语言

```
const express = require('express');
const csrf = require('csurf');
const cookieParser = require('cookie-parser');
const bodyParser = require('body-parser');

var csrfProtection = csrf({ cookie: true });
var parseForm = bodyParser.urlencoded({ extended: false });

var app = express();
app.set('view engine','ejs')

app.use(cookieParser());

app.get('/form', csrfProtection, function (req, res) {
  // pass the csrfToken to the view
  res.render('login', { csrfToken: req.csrfToken() });
});

app.post('/process', parseForm,
      csrfProtection, function (req, res) {
  res.send('Successfully Validated!!');
});

app.listen(3000, (err) => {
   if (err) console.log(err);
   console.log('Server Running');
});
```

1.  在上面的代码中，导入模块后，我们设置了路由中间件，并将验证方法作为 **cookie** 而不是**令牌**传递。**正文解析器**用于解析来自表单的数据。由于使用 **cookie** 作为验证方法，因此使用 **cookie 解析器**。现在，在**获取**请求中，我们将传递的 cookie 值呈现给视图。在 **POST** 请求中，我们首先验证 cookie，如果通过验证，我们将发送一条消息。

2.  现在，创建一个名为**的文件夹，查看**并创建一个名为 **login.ejs** 的文件，并在其中编写以下代码:

## 超文本标记语言

```
<html>
<head>
      <title>Csurf Middleware</title>
</head>
<body>
    <form action="process" method="POST">
       <input type="hidden" name="_csrf"
                value="<%= csrfToken %>">
       <input type="text" name="myname">
       <input type="submit" value="Submit">
    </form>
</body>
</html>
```