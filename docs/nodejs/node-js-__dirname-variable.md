# Node.js __dirname 变量

> 原文:[https://www.geeksforgeeks.org/node-js-__dirname-variable/](https://www.geeksforgeeks.org/node-js-__dirname-variable/)

**__dirname** 字符串给出了当前模块的目录路径，这也类似于文件名**的 **path.dirname()** 的路径。**

**返回值**:返回当前模块的目录路径。

**示例 1:** 让我们创建一个文件 main.js

## main.js

```js
import path from 'path';
const __dirname = path.resolve();
console.log(__dirname)
```

**输出:**现在运行**节点 main.js** 。

![](img/a0981d3240d4fab0a657ec6fd0bbb513.png)

**示例 2:** 用 path.dirname()复制 __dirname。

## java 描述语言

```js
import path from 'path';
const __dirname = path.resolve();
const __filename = path.resolve();
console.log(path.dirname(__filename));
```

**输出:**现在运行**节点 main.js** 。

![](img/a0981d3240d4fab0a657ec6fd0bbb513.png)

**参考:**[https://nodejs . org/docs/latest/API/globals . html # globals _ dirname](https://nodejs.org/docs/latest/api/globals.html#globals_dirname)