# node . js util . types . ismpiterer()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-ismpiterer-method/](https://www.geeksforgeeks.org/node-js-util-types-ismapiterator-method/)

**util . types . ismpiterer()方法**是 **util** 模块的内置应用编程接口，主要设计用于支持 **Node.js** 内部 API 的需求。

方法用于确定该值是否是为内置的[映射](https://www.geeksforgeeks.org/map-in-javascript/)实例返回的迭代器。

**语法:**

```js
util.types.isMapIterator( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**返回布尔值，即如果值是为内置**地图**返回的迭代器，则返回**真**，否则返回**假**。

下面的例子说明了在 Node.js 中使用**util . types . ismpiterer()**方法:

**例 1:**

```js
// Node.js program to demonstrate the 
// util.types.isMapIterator() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(true));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(new Map().values()));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(new Map().keys()));
```

**输出:**

```js
false
true
true

```

**例 2:**

```js
// Node.js program to demonstrate the 
// util.types.isMapIterator() method 

// Using require to access util module 
const util = require('util');

const map = new Map();

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(map.keys()));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(map.entries()));

// Using util.types.isMapIterator() method
console.log(util.types.isMapIterator(map[Symbol.iterator]()));
```

**输出:**

```js
true
true
true

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ ismpiterer _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_ismapiterator_value)