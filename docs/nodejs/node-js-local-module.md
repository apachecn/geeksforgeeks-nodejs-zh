# Node.js 本地模块

> 原文:[https://www.geeksforgeeks.org/node-js-local-module/](https://www.geeksforgeeks.org/node-js-local-module/)

Node.js 自带不同的预定义模块(例如 http、fs、path 等)。)我们使用并扩展我们的项目。我们可以在本地将模块定义为本地模块。它由在一个 JavaScript 对象中声明的不同函数组成，我们根据需求重用它们。我们也可以用 NPM 包装和分发。

**定义本地模块:**本地模块必须写在单独的 JavaScript 文件中。在单独的文件中，我们可以用不同的属性和方法声明一个 JavaScript 对象。

**步骤 1:** 用文件名`Welcome.js`创建一个本地模块

```js
const welcome = {

    sayHello : function() {
        console.log("Hello GeekforGeeks user");
  },

  currTime : new Date().toLocaleDateString(),

  companyName : "GeekforGeeks"
}

module.exports = welcome
```

**解释:**这里，我们用一个函数 sayHello 和两个变量 currTime 和 companyName 声明了一个对象‘welcome’。我们使用 module.export 使该对象全局可用。

**第二部分:**在这一部分中，使用 app.js 文件中的上述模块。

```js
var local = require("./Welcome.js");
local.sayHello();
console.log(local.currTime);
console.log(local.companyName);
```

**说明:**这里，我们将我们的局部模块‘say hello’导入到变量‘local’中，并消费所创建模块的函数和变量。
T3】输出:

```js
Hello GeekforGeeks user
12/6/2019
GeekforGeeks

```