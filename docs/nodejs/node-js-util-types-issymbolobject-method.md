# node . js util . types . issymbolobject()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-issymbolobject-method/](https://www.geeksforgeeks.org/node-js-util-types-issymbolobject-method/)

**util.types.isSymbolObject()方法**是 **util** 模块的一个内置应用编程接口，主要是为了支持 **Node.js** 自身内部 API 的需求而设计的。

**util.types.isSymbolObject()方法**用于确定该值是否为符号对象。

**语法:**

```js
util.types.isSymbolObject( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**返回布尔值，即仅当值是符号对象时返回**真**，否则返回**假**。

**注意:**符号对象是通过在符号基元上调用**对象()**来创建的。

下面的例子说明了在 Node.js 中 **util.types.isSymbolObject()方法**的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// util.types.isSymbolObject() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isSymbolObject() method
console.log(util.types.isSymbolObject(new Map()));

// Using util.types.isSymbolObject() method
console.log(util.types.isSymbolObject(Object({'geeks': 1})));

// Using util.types.isSymbolObject() method
console.log(util.types.isSymbolObject(Object(Symbol('geeks'))));
```

**输出:**

```js
false
false
true

```

**例 2:**

```js
// Node.js program to demonstrate the 
// util.types.isSymbolObject() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isSymbolObject() method
console.log(util.types.isSymbolObject(new Map()));

// Creating a symbol
const symbol = Symbol('GeeksforGeeks');

// Using util.types.isSymbolObject() method
console.log(util.types.isSymbolObject(symbol));

// Using util.types.isSymbolObject() method
console.log(util.types.isSymbolObject(Object(symbol)));
```

**输出:**

```js
false
false
true

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ issymbolobject _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_issymbolobject_value)