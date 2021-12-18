# node . js util . types . isnumberobject()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is numberobject-method/](https://www.geeksforgeeks.org/node-js-util-types-isnumberobject-method/)

util 模块的 **util.types.isNumberObject()方法**主要是为了支持 Node.js 自带的内部 API 的需求而设计的。用于检查通过的**值**是否为**号**对象。

**语法**

```
util.types.isNumberObject( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何数字，即任何模块的实例。

**返回值:**如果传递的值是 Number 对象，该方法返回一个布尔值，即 **true** ，否则返回 **false** 。

下面的例子说明了 **util.types.isNumberObject()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// util.types.isNumberObject() method

// It includes util module
const util = require('util');

// Returns false as it is not a number object
console.log(util.types.isNumberObject(0));

// Returns true as it is a number object
console.log(util.types.isNumberObject(new Number(0)));
```

**输出:**

```
false
true
```

**例 2:**

```
// Node.js program to demonstrate the   
// util.types.isNumberObject() method

// It includes util module
const util = require('util');

// Returns false becaluse it is not a number object
console.log(util.types.isNumberObject(100));

// Returns true because it is a number object
console.log(util.types.isNumberObject(new Number(12345678)));

// returns false because it is not a number object
console.log(util.types.isNumberObject(1.8));

// Returns true because it is a number object
console.log(util.types.isNumberObject(new Number(1.8)));

// Returns false as Number() method just convert
// string to number not to Number Object
console.log(util.types.isNumberObject(Number('1.8')));
```

**输出:**

```
false
true
false
true
false
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isnombobobject _ value](https://nodejs.org/api/util.html#util_util_types_isnumberobject_value)