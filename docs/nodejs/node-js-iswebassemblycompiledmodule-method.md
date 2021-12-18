# node . js iswebassembly compiled module()方法

> 原文:[https://www . geesforgeks . org/node-js-isweabassemblycompiled module-method/](https://www.geeksforgeeks.org/node-js-iswebassemblycompiledmodule-method/)

它是一个通过检查模块是否内置于网络程序集来返回真或假的函数。模块实例。

它检查给定的模块是否是网络程序集的实例。组件

**语法:**

```js
util.types.isWebAssemblyCompiledModule(module);
```

**参数**

*   **Value:** This value parameter is of any type. It is to check the value of the function.

**返回值:**

*   如果该值是内置的网络程序集，则为 True。模块实例。
*   如果该值不是内置的网络程序集，则为 False。模块实例。

**示例 1:Filename index . js**

```js
const util = require('util')
const morgan = require('morgan');
const mongoose = require('mongoose')

console.log(util.types
  .isWebAssemblyCompiledModule(morgan));
console.log(util.types
  .isWebAssemblyCompiledModule(mongoose));
```

**输出:**

```js
false
false
```

**示例 2:Filename index . js**

```js
const util = require('util')
const a = require('./a.js'); 

if(util.types.isWebAssemblyCompiledModule(a)) {
    console.log("It is an web assembly module instance")
} else {
    console.log("It is not an web assembly module instance")
}
```

要运行文件，请使用以下命令:

```js
node index.js
```

**输出:**

```js
It is not an web assembly module instance
```

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isweb assembly compiled module _ value