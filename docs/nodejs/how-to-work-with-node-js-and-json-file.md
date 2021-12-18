# 如何使用 Node.js 和 JSON 文件？

> 原文:[https://www . geesforgeks . org/如何使用节点-js-and-json-file/](https://www.geeksforgeeks.org/how-to-work-with-node-js-and-json-file/)

**Node.js** 是一个建立在 Chrome 的 V8 JavaScript 引擎上的 JavaScript 运行时。使用 node.js 作为后端，开发人员可以用 javaScript 为整个应用程序维护一个单独的代码库。
**JSON** 则代表 JavaScript 对象符号。这是一种存储和交换数据的轻量级格式。
**创建脚本:** Node.js 脚本以 js 文件扩展名创建。以下是存储为 *app.js* 文件的示例脚本。把你的主可执行文件写成 *app.js* 是一个常见的约定。

## java 描述语言

```js
console.log('Hello Node.js!');
```

**运行脚本:**我们可以使用 node app.js 命令运行 Node.js 脚本。打开终端窗口，导航到脚本所在的目录。

**输出:**

```js
Hello Node.js
```

**导入 Node.js 核心模块:** Node.js 包含一些内置模块。这些模块随节点一起提供，因此不需要安装。最常用的模块之一是文件系统或 *fs* 模块。 *fs* 模块提供了一个与文件系统交互的应用编程接口，或者基本上它提供了我们可以用来操作文件系统的功能。为了导入任何模块，我们使用 require()函数。脚本使用*writelefilesync*向 demo.txt 写一条消息，运行脚本后，我们会发现 demo.txt 文件，其中写入的数据与*writelefilesync*函数中给定的参数相同。如果目录中不存在“demo.txt”文件，则会创建一个同名的新文件。

## java 描述语言

```js
const fs = require('fs')

//  Writing to a file
fs.writeFileSync('demo.txt', 'geeks')
```

**从文件导出:***模块.导出*是一个内置节点包的对象。要在另一个文件中使用任何函数，我们必须从具有其定义的文件中导出它，并将其导入到我们希望使用它的文件中。

## java 描述语言

```js
// File Name: index.js
const demo = () => {
  console.log('This Functions uses'
          + ' ES6 arrow operator');
}

// We can export multiple functions
// by exporting an object of functions
// instead of a simple function

module.exports = check
```

**导入我们自己的文件:***需要的*功能也可以用来加载我们自己的 JavaScript 文件。我们必须提供要加载脚本的文件的相对路径。

## java 描述语言

```js
// File Name : app.js

// This index variable can be used
// to access all the exported methods
// of index.js in this file.
const index = require('./index.js');

// Executes all the functions
// contained in index.js
index();

// For any specific function use:
// Imported_variable.function_name()
index.check();
```

**编写和读取 JSON 文件:** JavaScript 提供了两种使用 JSON 的方法。第一个是*JSON . stringy*，第二个是 *JSON.parse* 。 *JSON.stringify* 将 JavaScript 对象转换为 JSON 字符串，而 *JSON.parse* 将 JSON 字符串转换为 JavaScript 对象。因为 JSON 只不过是一个字符串，所以它可以用来在文本文件中存储数据。
下面的代码只有在 data.json 文件作为*write filestync*存在的情况下才起作用，如果不存在，则不会创建 json 文件。如果只存在文本文件，则创建一个文件。

## java 描述语言

```js
// Importing 'fs' module
const fs = require("fs");

const geeksData = { title: "Node",
        article: "geeksforgeeks" };

// Covert JavaScript object into JSON string
const geeksJSON = JSON.stringify(geeksData);

// Covert JSON string into object
const geeksObject = JSON.parse(geeksJSON);
console.log(geeksObject.article);

// Adding more properties to JSON object
geeksObject.stack = "js";
geeksObject.difficulty = 1;

// Converting js object into JSON string
// and writing to data.json file
const dataJSON = JSON.stringify(geeksObject);
fs.writeFileSync("data.json", dataJSON);
console.log(geeksObject);
```

**运行代码的命令:**

```js
node app.js
```

**输出:**

```js
geeksforgeeks { 
    title: 'Node', 
    article: 'geeksforgeeks', 
    stack: 'js', 
    difficulty: 1 
} 
```