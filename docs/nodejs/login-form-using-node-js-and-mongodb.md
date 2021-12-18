# 使用 Node.js 和 MongoDB 的登录表单

> 原文:[https://www . geesforgeks . org/log in-form-use-node-js-and-MongoDB/](https://www.geeksforgeeks.org/login-form-using-node-js-and-mongodb/)

按照这些简单的步骤学习如何使用 Node.js 和 MongoDB 创建登录表单。登录表单允许用户在使用注册表单创建帐户后登录网站。
**模块安装:**

```js
$ npm install ejs
```

*   嵌入式 JavaScript 允许您使用普通 javaScript 生成 HTML 标记。

```js
$ npm install express --save
```

*   Express 是 Node 的一个模块框架，可以用于应用程序。

```js
$ npm install mongoose
```

*   Mongoose 是一个针对 MongoDB 和 Node.js 的对象数据建模(ODM)库，它管理数据之间的关系，提供模式验证，并用于在代码中的对象和 MongoDB 中这些对象的表示之间进行转换。

```js
$ npm install body-parser --save
```

*   Body-parser 允许 express 读取 Body，然后将其解析为我们可以理解的 JSON 对象。

```js
npm install express-session --save
```

*   Express.js 使用 cookie 来存储会话 id。

```js
npm install passport passport-local --save
npm install passport-local-mongoose --save
```

*   Passport 是节点的认证中间件。js。Passport 非常灵活和模块化，可以不引人注目地插入到任何基于 Express 的网络应用程序中。一套全面的策略支持使用用户名和密码、脸书、推特等进行身份验证。

**文件名:app.js**

## java 描述语言

```js
var express = require("express"),
    mongoose = require("mongoose"),
    passport = require("passport"),
    bodyParser = require("body-parser"),
    LocalStrategy = require("passport-local"),
    passportLocalMongoose =
        require("passport-local-mongoose"),
    User = require("./models/user");

mongoose.set('useNewUrlParser', true);
mongoose.set('useFindAndModify', false);
mongoose.set('useCreateIndex', true);
mongoose.set('useUnifiedTopology', true);
mongoose.connect("mongodb://localhost/auth_demo_app");

var app = express();
app.set("view engine", "ejs");
app.use(bodyParser.urlencoded({ extended: true }));

app.use(require("express-session")({
    secret: "Rusty is a dog",
    resave: false,
    saveUninitialized: false
}));

app.use(passport.initialize());
app.use(passport.session());

passport.use(new LocalStrategy(User.authenticate()));
passport.serializeUser(User.serializeUser());
passport.deserializeUser(User.deserializeUser());

//=====================
// ROUTES
//=====================

// Showing home page
app.get("/", function (req, res) {
    res.render("home");
});

// Showing secret page
app.get("/secret", isLoggedIn, function (req, res) {
    res.render("secret");
});

// Showing register form
app.get("/register", function (req, res) {
    res.render("register");
});

// Handling user signup
app.post("/register", function (req, res) {
    var username = req.body.username
    var password = req.body.password
    User.register(new User({ username: username }),
            password, function (err, user) {
        if (err) {
            console.log(err);
            return res.render("register");
        }

        passport.authenticate("local")(
            req, res, function () {
            res.render("secret");
        });
    });
});

//Showing login form
app.get("/login", function (req, res) {
    res.render("login");
});

//Handling user login
app.post("/login", passport.authenticate("local", {
    successRedirect: "/secret",
    failureRedirect: "/login"
}), function (req, res) {
});

//Handling user logout
app.get("/logout", function (req, res) {
    req.logout();
    res.redirect("/");
});

function isLoggedIn(req, res, next) {
    if (req.isAuthenticated()) return next();
    res.redirect("/login");
}

var port = process.env.PORT || 3000;
app.listen(port, function () {
    console.log("Server Has Started!");
});
```

**文件名:home.ejs**

## 超文本标记语言

```js
<h1>This is home page</h1>

<li><a href="/register">Sign up!!</a></li>
<li><a href="/login">Login</a></li>
<li><a href="/logout">Logout</a></li>
```