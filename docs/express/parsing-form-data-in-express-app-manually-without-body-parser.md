# 无需正文解析器，手动解析快递 app 中的表单数据

> 原文:[https://www . geesforgeks . org/parsing-form-data-in-express-app-manual-not-body-parser/](https://www.geeksforgeeks.org/parsing-form-data-in-express-app-manually-without-body-parser/)

**解析**是指以 HTML 形式访问用户提交的数据。当使用“GET”方法提交表单时，数据被附加到“查询字符串”中，并且可以轻松访问，但是当使用“POST”方法提交表单时，由于出于安全目的对这些数据进行了编码，因此很难访问这些数据。
有一个 body-parser NPM 方法，它使解析数据变得非常容易，但是如果我们试图从头开始实现这个解析方法，需要一些步骤。

**步骤:**

*   安装快速包

```js
npm install express
```

*   正在启动快速服务器(设置应用程序侦听器)

```js
app.listen(PORT, callback)
```

*   为“POST”表单提交和设置中间件函数调用创建路由

```js
app.post(path, middleware, callback)
```

*   创建中间件解析函数
    *   超出编码表单数据 aap.on()方法。
    *   使用 decodeURIComponent()方法将编码数据转换为字符串。
    *   创建一个用户提交数据的对象，并将其分配给请求对象的 req.body。

**示例 1:** 本示例创建登录表单。

**档案:loginForm .例**

## 超文本标记语言

```js
<!DOCTYPE html>
<html lang="en">

<head>
    <title>Form data parsing</title>
</head>

<body>
    <form action='information' method='POST'>
        <div>
            <label id='username'>Username</label>
            <div>
                <input type='text' for='username'
                    placeholder='Username'
                    name='username'>
            </div>
        </div>

        <div>
            <label class='label' id='password'>
                Password
            </label>

            <div>
                <input class='input'
                    type='password'
                    for='password'
                    placeholder='Password'
                    name='password'>
            </div>
        </div>

        <div class='buttons'>
            <button>Login</button>
        </div>
    </form>
</body>

</html>
```