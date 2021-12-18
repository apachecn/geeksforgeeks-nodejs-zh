# Node.js 提示. addProperties()方法

> 原文:[https://www . geesforgeks . org/node-js-prompt-add properties-method/](https://www.geeksforgeeks.org/node-js-prompt-addproperties-method/)

**prompt.addProperties()方法**是一个异步函数，该方法用于从命令行向现有对象添加属性。该功能用于输入/输出操作。

**语法:**

```js
prompt.addProperties(object, Array[keys], callbackfunction)

```

**参数:**该方法取如下三个参数:

1.  **对象:**第一个参数是程序中预定义的对象。
2.  **数组:**第二个参数是给定对象的键。
3.  **回调函数:**回调函数使这个函数是一个异步函数。

**安装模块:**

1.  您可以访问[安装](https://www.npmjs.com/package/prompt)这个模块的链接。您可以使用此命令安装此软件包。

    ```js
    npm install prompt

    ```

2.  之后，您可以创建一个文件夹并添加一个文件，例如 index.js。

```js
node index.js

```

**项目:**

![](img/6d93e1db083f283e170a0b34893345d2.png)

**文件名索引. js**

```js
const prompt = require('prompt');

// Start the prompt
prompt.start();

// Create an object
const user = {
    name: 'GFG',
    country: 'India'
};

// Extending the `user` object
prompt.addProperties(user, ['email', 'age'], (err, user) => {
    if (err) {
        throw err;
    }

    // Printing modified object
    console.log(user);

});
```

**运行该程序的步骤:**
使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输入:**

```js
gfg112@gmail.com
prompt: age: 12

```

**输出:**

```js
prompt: email:  test@gmail.com
prompt: age:  12
{ name: 'GFG', country: 'India', email: 'test@gmail.com', age: '12' }

```