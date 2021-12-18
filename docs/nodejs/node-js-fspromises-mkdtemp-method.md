# Node.js fsPromises.mkdtemp()方法

> 原文:[https://www . geesforgeks . org/node-js-fspromises-mkdtemp-method/](https://www.geeksforgeeks.org/node-js-fspromises-mkdtemp-method/)

**fsPromises.mkdtemp()** 方法是一个内置方法，它创建一个唯一的临时目录，并用创建的目录路径解析*promises*。

**语法:**

```js
fs.Promises.mkdtemp( prefix, options )
```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **Prefix:** is a string representing the file path.
*   **option: whether** is a string or an object.
    *   **code:** is a character string, and the default is **UTF8\.**

**返回值:**它返回*承诺*对象，该对象表示异步操作的最终完成(或失败)及其结果值。

**示例:**可以使用以下代码创建临时目录:

```js
// Node.js program to demonstrate the 
// fsPromises.mkdtemp() method 
const fs = require("fs");

const fsPromises = fs.promises;
const prefix = "temp";

fsPromises.mkdtemp(prefix,{ encoding: "utf8"})
.then((folder)=>{
    console.log("Temp folder created ", folder)
})
.catch((err)=>{
    console.log(err)
});
);
```

**输出:**

```js
Temp folder created  tempoe5zc9
```

通过在提供的前缀末尾附加六个随机字符来生成唯一的目录名。由于平台不一致，请避免在前缀中尾随 X 字符。一些平台，特别是 BSDs，可以返回六个以上的随机字符，并用随机字符替换前缀中的尾随 X 字符。

可选选项参数可以是指定编码的字符串，也可以是具有指定要使用的字符编码的编码属性的对象。

```js
fsPromises.mkdtemp(path.join(os.tmpdir(), 'foo-'))
 .catch(console.error);

```

fsPromises.mkdtemp()方法会将六个随机选择的字符直接追加到前缀字符串中。例如，给定一个目录/tmp，如果打算在/tmp 中创建一个临时目录，前缀必须以一个特定于平台的路径分隔符结尾(require('path ')。sep)。