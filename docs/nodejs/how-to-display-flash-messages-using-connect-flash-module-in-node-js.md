# 如何使用 Node.js 中的连接闪存模块显示闪存消息？

> 原文:[https://www . geesforgeks . org/how-display-flash-messages-use-connect-flash-module-in-node-js/](https://www.geeksforgeeks.org/how-to-display-flash-messages-using-connect-flash-module-in-node-js/)

Node.js 的 Connect-flash 模块允许开发人员在用户重定向到指定网页时发送消息。例如，每当用户成功登录到他/她的账户时，一条消息**闪烁(显示)**指示他/她认证成功。
**先决条件**开始申请前，您必须具备以下条件:

1.  您选择的集成开发环境安装在您的系统中。
2.  安装并配置了 Node.js 和 NPM。
3.  Node.js 及其模块的基础知识。

**安装和设置:**首先，用 **package.json** 文件初始化我们的应用程序。然后通过以下命令安装我们的应用程序所需的依赖项:

```js
npm install express express-session connect-flash --save 
```

在这里，**快车**需要**连接-闪光**库运行。我们正在使用**快速会话**，这样，每当一条消息被刷新，用户被重定向到指定页面时，就可以创建一个会话。

现在，创建一个文件并将其命名为 **app.js** 。你可以说出你选择的任何名字。现在，打开 **app.js** 文件，通过以下代码导入模块:

## java 描述语言

```js
const express = require('express');
const session = require('express-session');
const flash = require('connect-flash');

const app = express();
```