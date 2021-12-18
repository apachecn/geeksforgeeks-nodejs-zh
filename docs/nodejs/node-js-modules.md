# Node.js 模块

> 原文:[https://www.geeksforgeeks.org/node-js-modules/](https://www.geeksforgeeks.org/node-js-modules/)

在 Node.js 中，**模块**是封装的代码块，它们根据相关的功能与外部应用程序进行通信。模块可以是单个文件或多个文件/文件夹的集合。程序员严重依赖模块的原因是因为它们的可重用性以及将一段复杂的代码分解成可管理的块的能力。

**模块有三种类型:**

*   核心模块
*   本地模块
*   第三方模块

**核心模块:** Node.js 有很多内置模块，是平台的一部分，自带 Node.js 安装。这些模块可以通过使用**需求**功能加载到程序中。

**语法:**

```js
var module = require('module_name');
```

require()函数将根据特定模块返回的内容返回一个 JavaScript 类型。下面的例子演示了如何使用 Node.js Http 模块创建一个 web 服务器。

```js
var http = require('http');
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/html'});
  res.write('Welcome to this page!');
  res.end();
}).listen(3000);
```

在上面的例子中，require()函数返回一个对象，因为 Http 模块将其功能作为一个对象返回。当有人试图访问端口 3000 上的计算机时，将执行函数 http.createServer()方法。res.writeHead()方法是状态代码，其中 200 表示可以，而第二个参数是包含响应头的对象。

下面的列表包含了 Node.js 中一些重要的核心模块:

| 核心模块 | 描述 |
| --- | --- |
| 超文本传送协议（Hyper Text Transport Protocol 的缩写） | 在 Node.js 中创建一个 HTTP 服务器 |
| 维护 | 一组对测试有用的断言函数。 |
| 满量程 | 用于处理文件系统。 |
| 小路 | 包括处理文件路径的方法。 |
| 过程 | 提供关于当前 Node.js 进程的信息和控制。 |
| 操作系统（Operating System） | 提供有关操作系统的信息。 |
| 查询字符串 | 用于解析和格式化网址查询字符串的实用程序。 |
| 全球资源定位器(Uniform Resource Locator) | 模块为 URL 解析和解析提供实用程序。 |

**本地模块:**与内置和外部模块不同，本地模块是在 Node.js 应用程序中本地创建的。让我们创建一个简单的计算模块来计算各种运算。创建具有以下代码的 calc.js 文件:

**档案名称:calc.js**

```js
exports.add = function (x, y) { 
    return x + y; 
}; 

exports.sub = function (x, y) { 
    return x - y; 
}; 

exports.mult = function (x, y) { 
    return x * y; 
}; 

exports.div = function (x, y) { 
    return x / y; 
};
```

由于此文件通过导出向外部世界提供属性，因此另一个文件可以使用 require()函数使用其导出的功能。

**文件名:index.js**

```js
var calculator = require('./calc'); 

var x = 50, y = 10; 

console.log("Addition of 50 and 10 is "
                   + calculator.add(x, y)); 

console.log("Subtraction of 50 and 10 is "
                   + calculator.sub(x, y)); 

console.log("Multiplication of 50 and 10 is "
                   + calculator.mult(x, y)); 

console.log("Division of 50 and 10 is " 
                   + calculator.div(x, y)); 
```

**运行该程序的步骤:**使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
Addition of 50 and 10 is 60
Subtraction of 50 and 10 is 40
Multiplication of 50 and 10 is 500
Division of 50 and 10 is 5

```

**注意:**该模块还隐藏了模块外不需要的功能。

**第三方模块:**第三方模块是使用节点包管理器(NPM)在线提供的模块。这些模块可以安装在项目文件夹中，也可以全局安装。一些流行的第三方模块是猫鼬、快车、角车和反应车。

**示例:**

*   npm 快速安装
*   npm 安装猫鼬
*   npm 安装-g @angular/cli