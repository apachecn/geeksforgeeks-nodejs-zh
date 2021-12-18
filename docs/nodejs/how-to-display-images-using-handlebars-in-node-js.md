# 如何在 Node.js 中使用手柄显示图像？

> 原文:[https://www . geesforgeks . org/如何使用节点中的车把显示图像-js/](https://www.geeksforgeeks.org/how-to-display-images-using-handlebars-in-node-js/)

在本文中，我们将讨论如何使用 Node.js 中的[车把](https://www.geeksforgeeks.org/handlebars-templating-in-expressjs/)来显示图像。您可以参考[这篇](https://www.geeksforgeeks.org/how-to-setup-handlebars-view-engine-in-node-js/)文章来设置 Node.js 中的车把视图引擎。

我们将使用以下步骤来实现我们的目标:

1.  Install courier and courier handlebars
2.  Set up our courier server.
3.  Create the folder structure of the basic handlebar
4.  Define the right route.

**安装快递和快递车把:**

```
npm install --save express express-handlebars
```

**设置快递服务器:**

## Javascript

```
//importing modules
import express from "express"
import path from "path"
import exphbs from "express-handlebars"

// Express server's instance
const app = express();

const PORT = process.env.PORT || 3000;

// listening
app.listen(PORT, () => console.log(`Server started running on PORT ${PORT}`));
```