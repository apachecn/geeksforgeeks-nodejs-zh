# Express.js req .子域属性

> 原文:[https://www . geesforgeks . org/express-js-req-子域-property/](https://www.geeksforgeeks.org/express-js-req-subdomains-property/)

**req .子域**属性在请求的域名中包含一个子域数组。应用程序属性子域偏移，默认为 2，决定子域段的开始。

**语法:**

```
req.subdomains

```

**参数:**无参数。
**退货:**阵列
**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

```
npm install express

```

1.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

```
npm version express

```

1.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```
node index.js

```

**示例 1:**
**文件名:index.js**

## java 描述语言

```
var express = require('express');
var app = express();
var PORT = 3000;

app.get('/', function (req, res) {
  console.log(req.subdomains);
  res.send();
});

app.listen(PORT, function(err){
    if (err) console.log(err);
    console.log("Server listening on PORT", PORT);
});
```