# node . js util . types . ismmodulenamespaceobject()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-ismmodulenamespaceobject-method/](https://www.geeksforgeeks.org/node-js-util-types-ismodulenamespaceobject-method/)

该函数用于检查以下对象是否为**模块命名空间对象的实例。**如果该值是模块名称空间对象的实例，则该函数返回真值。

**语法:**

```js
util.types.isModuleNamespaceObject( value ); 
```

**参数:**

*   **Value:** This value parameter is of any type. It is to check the value of the function.

**返回值:**该函数返回布尔值。根据对象是否是模块命名空间对象，它返回真或假。

**示例 1:** **文件名:index.js**

```js
// Requiring module
const util = require('util');
const mongoose = require('mongoose')

console.log(util.types.isModuleNamespaceObject(mongoose))
console.log(util.types.isModuleNamespaceObject(util))
```

**输出:**

```js
false
false

```

**示例 2:** **文件名:**

```js
// Requiring file
const b = require('./index.js');
// The index.js can be anyfile located in 
// the directory where the code resides

// Requiring module
const util = require('util')

if (util.types.isModuleNamespaceObject(b)) {
   console.log("It is a namespaceobject module")
} else {
   console.log("It is not a namespace object module")
}
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
It is not a namespaceobject module
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ ismodulenamespaceobject _ value](https://nodejs.org/api/util.html#util_util_types_ismodulenamespaceobject_value)