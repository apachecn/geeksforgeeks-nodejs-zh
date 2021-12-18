# 如何在 Node.js 中包含来自其他文件的函数？

> 原文:[https://www . geesforgeks . org/如何从节点中的其他文件中包含函数-js/](https://www.geeksforgeeks.org/how-to-include-functions-from-other-files-in-node-js/)

代码可重用性是现代编程的一个重要支柱。**代码重用**是指将现有代码用于新功能或软件的实践。在本文中，我们将学习如何使用**节点. js** 中其他文件的函数。

使用内置的**导出**和**需要 **Node.js.** 的**功能，可以轻松实现该功能

**导出:****节点**中的**模块.导出**用于将任何文字、函数或对象作为模块导出。它用于将 JavaScript 文件包含到 Node.js 应用程序中。该模块类似于用于表示当前模块的变量，并导出作为模块公开的对象。

**Require()函数:**它是一个内置函数，是包含存在于单独文件中的函数的最简单方法。require 的基本功能是读取一个 JavaScript 文件，执行该文件，然后返回导出对象。

让我们考虑以下基本示例:

**文件名:cal.js**

```
function sum(x, y) {
    return (x + y);
}

function sub(x, y) {
    return (x - y);
}

function mul(x, y) {
    return (x * y);
}

module.exports = { add, sub, mul, div };
```

在上面的例子中，我们使用了 module.exports 函数，这样我们就可以在其他文件中使用它。根据一次导出多个函数的格式，函数被括在花括号({ })中。

假设我们想在 **main.js、**中使用这些函数，那么可以使用以下代码轻松完成:

**文件名:main.js**

```
//requiring cal.js file
const cal = require("./cal.js")  

//Using the functions from cal.js 
const sum = cal.sum(2, 2);
console.log(sum); 

const sub = cal.sub(10, 5);
console.log(sub); 

const product = cal.mul(2, 3);
console.log(product);
```

这会将 **cal.js** 文件及其**功能**导入到 **main.js** 文件中。

使用以下命令运行 **main.js** 文件:

```
node main.js
```

**输出:**

```
4
5
6

```