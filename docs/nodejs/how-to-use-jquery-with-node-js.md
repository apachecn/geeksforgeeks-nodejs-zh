# 如何用 Node.js 使用 jQuery？

> 原文:[https://www . geeksforgeeks . org/如何使用-带节点的 jquery-js/](https://www.geeksforgeeks.org/how-to-use-jquery-with-node-js/)

**jQuery** 是一个 JavaScript 库，它为我们提供了与普通 JavaScript 相同的功能，但是代码行更少。对 jQuery 的需求减少了，因为在普通的带有更新的 JavaScript 中做事情变得简单多了。尽管它的受欢迎程度在下降，但仍有大约 76%的项目使用 jQuery。

**我们的目标是在 Node.js 中使用 jQuery:**我们可以使用 [jquery](https://www.npmjs.com/package/jquery) 模块在 Node.js 中使用 jQuery。

**注意:**使用“jquery”模块，而不是“jQuery”模块，因为后者已被否决。

**让 jQuery 在 Node.js 中工作:**

*   **第一步:**制作 package.json 文件。使用以下命令创建 package.json 文件，该文件跟踪模块和依赖关系。

    ```
    npm init -y
    ```

    “-y”标记使 yes 成为创建 package.json 文件时所有问题的默认答案。

*   **步骤 2:** 安装 jquery 模块。使用以下命令安装 jquery 模块。

    ```
    npm install jquery
    ```

*   **步骤 3 :** 安装 jsdom 模块。由于 jQuery 是一个前端 JavaScript 库，它需要一个包含文档的窗口才能在后端工作。“jsdom”是一个用来解析 HTML 并与之交互的库。它不完全是一个网络浏览器，而是模仿一个。使用以下命令安装 jsdom 模块。

    ```
    npm install jsdom
    ```

*   **第 4 步:**导入 jsdom 模块。使用 require 方法导入 jsdom 模块。

    ```
    const jsdom = require('jsdom')
    ```

*   **步骤 5:** 创建新窗口。我们通过创建一个 JSDOM 对象，用 HTML 代码作为参数，创建一个带有文档的窗口。以下代码用于创建带有文档的窗口:-

    ```
    const dom = new jsdom.JSDOM("")
    ```

*   **第六步:**导入 jQuery 并提供窗口。一旦创建了包含文档的窗口，我们就可以通过向 jquery 模块提供我们创建的窗口来使用它。下面的代码用于导入 jquery 模块。

    ```
    const jquery = require('jquery')(dom.window)
    ```

就这样，我们成功地将 jquery 加载到了 Node.js 应用程序中。

**示例:**为了更好地理解其工作原理，请浏览以下示例:-

## java 描述语言

```
// Importing the jsdom module
const jsdom = require("jsdom");

// Creating a window with a document
const dom = new jsdom.JSDOM(`<!DOCTYPE html>
<body>
<h1 class="heading">
    GeeksforGeeks
</h1>
</body>
`);

// Importing the jquery and providing it
// with the window
const jquery = require("jquery")(dom.window);

// Appending a paragraph tag to the body
jquery("body").append("<p>Is a cool Website</p>");

// Getting the content of the body
const content = dom.window.document.querySelector("body");

// Printing the content of the heading and paragraph
console.log(content.textContent);
```

**输出:**

```
GeeksforGeeks
Is a cool website
```