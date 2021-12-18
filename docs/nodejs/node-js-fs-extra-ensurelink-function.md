# Node.js fs-extra ensureLink()函数

> 原文:[https://www . geesforgeks . org/node-js-fs-extra-ensurelink-function/](https://www.geeksforgeeks.org/node-js-fs-extra-ensurelink-function/)

**确保链接()**功能确保给定的两个文件之间的链接存在。如果目标文件不存在，它将被创建并在它们之间创建一个链接，但是如果源文件不存在，函数将抛出一个错误。如果目标文件的目录结构不存在，它将被创建。通过链接，这意味着两个链接的文件将是彼此的副本。如果一个文件中有任何更改，它也会反映在另一个文件中。 **createLink()** 是该函数的另一个名称。

**语法:**

```js
fs.ensureLink(srcPath,destPath,callback)
```

```js
fs.createLink(srcPath,destPath,callback)
```

**参数:**该函数接受三个参数，如上所述，如下所述。

*   **srcPath:** 它是一个字符串，包含要与另一个文件链接的文件的路径。这个文件需要存在，否则函数会抛出一个错误。
*   **destPath:** 它是一个字符串，包含将链接到 srcPath 中指定的文件的另一个文件的路径。
*   **回调:**链接建立后或执行过程中出现错误时调用。承诺也可以用来代替回调函数。

**返回值:**不返回任何东西。

**按照步骤实现功能:**

1.  可以使用以下命令安装该模块:

    ```js
    npm install fs-extra
    ```

2.  安装模块后，您可以使用以下命令检查已安装模块的版本:

    ```js
    npm ls fs-extra
    ```

    ![](img/6f9698d7807d36e8a1b1743c10a22d3c.png)

3.  使用以下命令创建一个名为 index.js 的文件，并在文件中要求 fs-extra 模块:

    ```js
    const fs = require('fs-extra');
    ```

4.  要运行文件，请在终端中写入以下命令:

    ```js
    node index.js
    ```

**项目结构:**项目结构会是这样的。

![](img/5a04b4a9423b0180bdb62b253dc661e9.png)

**示例 1:** 创建一个名为 file.txt 的文件和一个名为 des 的文件夹，并在文件夹内部创建一个名为 file.txt 的文件。我们将在已经存在的文件上尝试该功能。

## index.js

```js
// Requiring module
const fs = require("fs-extra");

// source file path
// File needs to exist
const src = "file.txt";
// destination file path
const dest = "des/file.txt";

// Function Call
// Using callback function
fs.ensureLink(src, dest, (err) => {
  if (err) return console.log(err);
  console.log("Success! Both files are now linked");
});
```