# node . js util . types . issetitor()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-issetiterer-method/](https://www.geeksforgeeks.org/node-js-util-types-issetiterator-method/)

**util . types . issetiteerator()方法**是 **util** 模块的内置应用编程接口，主要是为了支持 **Node.js** 自身的内部 API 的需求而设计的。

方法用于确定该值是否是为内置的**集**实例返回的迭代器。

**语法:**

```
util.types.isSetIterator( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**它返回一个布尔值，即如果值是为内置**集**实例返回的迭代器，则返回**真**，否则返回**假**。

下面的例子说明了在 Node.js 中使用**util . types . issetitor()方法**:

**例 1:**

```
// Node.js program to demonstrate the 
// util.types.isSetIterator() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(true));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(new Set().values()));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(new Set().keys()));
```

**输出:**

```
false
true
true

```

**例 2:**

```
// Node.js program to demonstrate the 
// util.types.isSetIterator() method 

// Using require to access util module 
const util = require('util');

const set = new Set();

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(set.keys()));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(set.entries()));

// Using util.types.isSetIterator() method
console.log(util.types.isSetIterator(set[Symbol.iterator]()));
```

**输出:**

```
true
true
true

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ issetitor _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_issetiterator_value)