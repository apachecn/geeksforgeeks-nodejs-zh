# express . js app . local Property

> 原文:[https://www . geesforgeks . org/express-js-app-locals-property/](https://www.geeksforgeeks.org/express-js-app-locals-property/)

对象的属性是应用程序中的局部变量。这些变量是应用程序的本地变量，非常有用。

**语法:**

```js
app.locals
```

**参数:**无参数。

**返回值:**对象

**快递模块安装:**

1.  您可以访问[安装快速模块](https://www.npmjs.com/package/express)的链接。您可以使用此命令安装此软件包。

    ```js
    npm install express
    ```

2.  安装快速模块后，您可以使用命令在命令提示符下检查您的快速版本。

    ```js
    npm version express
    ```

3.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

    ```js
    node index.js
    ```

**示例 1:** **文件名:index.js**

```js
var express = require('express');
var app = express();

// Setting single locals variable
app.locals.email = 'demo@gmail.com' 

console.log(app.locals.email);
```

**运行程序的步骤:**

1.  项目结构会是这样的:
    ![](img/3209d9b4369c180282a34be8070d7d6e.png)
2.  使用以下命令确保您已经安装了 **express** 模块:

    ```js
    npm install express
    ```

3.  Run index.js file using below command:

    ```js
    node index.js
    ```

    **输出:**

    ```js
    demo@gmail.com

    ```

**示例 2:** **文件名:index.js**

```js
var express = require('express');
var app = express();

// Setting multiple locals variable
app.locals.domain = 'www.sample.com' 
app.locals.age = '24' 
app.locals.company = 'ABC Ltd' 

console.log(app.locals);
```

使用以下命令运行 index.js 文件:

```js
node index.js
```

**输出:**

```js
[Object: null prototype] {
  settings: {
    'x-powered-by': true, 
    etag: 'weak',
    'etag fn': [Function: generateETag],
    env: 'development',
    'query parser': 'extended',
    'query parser fn': [Function: parseExtendedQueryString],
    'subdomain offset': 2,
    'trust proxy': false,
    'trust proxy fn': [Function: trustNone],
    view: [Function: View],
    views: 'C:\\Users\\Lenovo\\Downloads\\GFG 
      Reviewer Internship\\Program\\views',
    'jsonp callback name': 'callback'
  },
  domain: 'www.sample.com',
  age: '24',
  company: 'ABC Ltd'
}

```

**参考:**[https://expressjs . com/en/4x/API . html # app . locals](https://expressjs.com/en/4x/api.html#app.locals)