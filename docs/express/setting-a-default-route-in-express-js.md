# 在 Express.js 中设置默认路线

> 原文:[https://www . geesforgeks . org/setting-a-default-route-in-express-js/](https://www.geeksforgeeks.org/setting-a-default-route-in-express-js/)

### 什么是默认路由？

正如我们所知，在一个快速应用程序中，涉及到如此多的网址和请求。用户可能找到了我们的快递应用程序中没有的路线。在这种情况下，用户会得到一个**错误**为了处理这类问题，我们为我们的快递 app 设置了一个默认路线，通知用户，他打错了路线或者将用户重定向到了一个特定的路线。

以下是用户遇到错误路线时的错误页面示例:

![](img/635e30da15b2b2d9008a8bbf40b6ab71.png)

定义默认路线时，请遵循以下**注意事项**:

*   您的 web 应用程序中只有一条默认路线。
*   默认路线将在应用程序的所有其他路线都已定义后定义，即在末端。

#### 在快速应用程序中设置默认路线的步骤:

**第一步**:创建你的项目文件夹。

**步骤 2** :现在在您的终端中，从项目文件夹的根目录运行以下命令:

```js
 $ npm init
```

**第 3 步**:使用以下命令安装 express:

```js
 $ npm install express
```

**第四步**:要求‘快递’，根据你的申请要求设置你所有的普通路线。

**第五步**:在所有路线下面，如下图设置你的默认路线:

```js
app.get(**"*"**, function (req, res) {
 res.render("Error_page"); 
});
```

**示例**:下面给出了一个默认路线的快递 app 示例。

**文件名:index.js**

## java 描述语言

```js
// Requiring modules
const express = require("express");
const app = express();

// Root route of express app
app.get("/", (req, res) => {
  res.send("Hello Geeks");
});

app.get("/new", (req, res) => {
  res.send("welcome to new page");
});

// All the general routes of your
// web app are defined above the
// default route

// Default route
app.get("*", (req, res) => {

  // Here user can also design an
  // error page and render it 
  res.send("PAGE NOT FOUND");
});

// Server setup
app.listen(3001, () => {
  console.log(
`Server listening on http://localhost:3001`);
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Server listening on http://localhost:3001
```

现在打开你的浏览器，导航到 **http://localhost:3001，**你会在屏幕上看到如下消息:

```js
Hello Geeks
```

现在点击除了我们定义的网址之外的任何不同的网址，就像这里我们点击了 **http://localhost:3001/xyz。**以下是您屏幕上的输出:

```js
PAGE NOT FOUND
```