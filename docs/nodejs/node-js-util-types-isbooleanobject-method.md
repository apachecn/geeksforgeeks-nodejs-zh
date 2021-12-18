# node . js util . types . IsBooleanObject()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is boolean object-method/](https://www.geeksforgeeks.org/node-js-util-types-isbooleanobject-method/)

**util.types.isBooleanObject()方法**是 **util** 模块的内置应用编程接口，主要是为了支持 **Node.js** 自身的内部 API 的需求而设计的。

**util.types.isBooleanObject()方法**用于确定该值是否为布尔对象。

**语法:**

```
util.types.isBooleanObject( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**返回布尔值，即如果值是布尔对象，则返回**真**，否则返回**假**。

下面的例子说明了在 Node.js 中使用 **util.types.isBooleanObject()方法**:

**例 1:**

```
// Node.js program to demonstrate the 
// util.types.isBooleanObject() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isBooleanObject() method
console.log(util.types.isBooleanObject(true));

// Using util.types.isBooleanObject() method
console.log(util.types.isBooleanObject("Map"));

// Using util.types.isBooleanObject() method
console.log(util.types.isBooleanObject(new Boolean(false)));
```

**输出:**

```
false
false
true

```

**例 2:**

```
// Node.js program to demonstrate the 
// util.types.isBooleanObject() method 

// Using require to access util module 
const util = require('util');

// Creating a Boolean Object
const a = new Boolean(true);

// Creating a Boolean Object
const b = new Boolean(false);

// A Boolean type variable
const c = true;

// Using util.types.isBooleanObject() method
console.log(util.types.isBooleanObject(a));

// Using util.types.isBooleanObject() method
console.log(util.types.isBooleanObject(b));

// Using util.types.isBooleanObject() method
console.log(util.types.isBooleanObject(c));
```

**输出:**

```
true
true
false

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ is pooleanobject _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_isbooleanobject_value)