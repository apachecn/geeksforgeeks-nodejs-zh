# NODE_ENV 变量及其使用方法？

> 原文:[https://www . geesforgeks . org/node _ env-变量和如何使用它们/](https://www.geeksforgeeks.org/node_env-variables-and-how-to-use-them/)

**简介:** NODE_ENV 变量是 express 框架做了推广的环境变量。这种类型的变量值可以根据程序运行的环境(即开发/生产)动态设置。NODE_ENV 的工作方式就像一个标志，指示服务器是在开发模式还是生产模式下运行。express 框架在运行时检查标志值，并根据环境设置值。

**设置 NODE_ENV 变量:**设置 NODE_ENV 变量取决于操作系统，也取决于用户的设置。

要将环境变量全局设置为某个值，我们可以从命令行运行代码。

**适用于 Linux 和 Mac 操作系统:**

```js
export NODE_ENV = production
```

**对于 Windows 操作系统**

```js
$env:NODE_ENV = 'production'
```

假设我们正在运行一个名为 *app.js* 的脚本，我们也可以使用下面的代码在应用程序初始化命令中应用环境变量。

```js
NODE_ENV = production node app.js
```

在 Windows 中，代码是不同的。我们使用下面的代码:

```js
set NODE_ENV=production&&node app.js
```

因为不同的操作系统需要不同的命令，所以有一个名为 [*【跨环境】*](https://www.npmjs.com/package/cross-env) 的包可以让命令跨平台。

```js
npx cross-env NODE_ENV=production node app.js
```

上面的代码可以在任何平台上工作，只要跨 env 包是作为开发人员依赖项安装的。

如果我们使用 express，我们可以提供特定于环境的设置，这些设置会根据我们工作的环境自动调用。

**语法:**

```js
if(process.env.NODE_ENV == 'development') {
   // Code for Development Mode
} else {
   // Code for Testing Mode
}
```

假设我们的数据库服务器是开发模式下的本地主机，我们将使用*https://production-server.com*进行生产。可以相应地设置代码。

```js
if(process.env.NODE_ENV == 'development') {
    db.connect('localhost:1234')
} else {
    db.connect('https://production-server.com')
}
```

上面的代码将检查环境并相应地设置它的服务器。

**结论:**使用生产环境是一种很好的做法，因为在生产环境中，通常日志记录保持在最低水平，并且会有更多的缓存级别来优化性能。因此，每当我们将应用程序部署到生产服务器时，将环境变量设置为生产模式总是一个好的做法。