# 如何在 Node.js 中刷新文件？

> 原文:[https://www . geesforgeks . org/如何刷新节点中的文件-js/](https://www.geeksforgeeks.org/how-to-refresh-a-file-in-node-js/)

Node.js 在过去几年中取得了重要的增长，并且仍然在许多组织和业务模型中增加其价值。像沃尔玛或贝宝这样的公司已经开始采用它。
NPM，当你安装 Node.js 的时候，Node.js 的包管理器已经安装好了，可以在你的电脑上运行了。Node.js 没有像其他语言(如 PHP 或 Ruby)那样为您提供自动重启的特权。每当您对源代码进行更改时，都需要使用命令一次又一次地运行代码。

我们大多数人习惯于在编辑器中保存文件，然后点击[ctrl + c](停止应用程序)，然后再次点击[向上箭头+回车]重新启动。然而，与其手动完成这个重复的任务，我们当然可以自动化它，并可以通过使用一些工具使这个过程更加容易:

1.  nodemon(节点名)
2.  节点管理器
3.  永远

**1。nodemin:** 在所有这些工具中，我们想先从 nodemon 开始。基本上，Nodemon 是一个实用程序，它可以监视源中的任何更改，并自动重启服务器。

**安装命令:**

```
npm install nodemon -g
```

安装 nodemon 实用程序后，我们将使用以下命令运行代码。

```
nodemon filename.js
```

**2。节点-主管:**
**安装命令**

```
npm install supervisor -g
```

安装节点管理器后，我们将使用以下命令运行代码。

```
supervisor filename.js
```

**3。forever:** 剩下的所谓 forever 的工具是一个 node.js 包，用于保持服务器活动，即使当它因为一些错误/异常而崩溃或停止时。永远自动重启。
**安装命令**

```
npm install forever -g
```

```
frorever start filename.js
```