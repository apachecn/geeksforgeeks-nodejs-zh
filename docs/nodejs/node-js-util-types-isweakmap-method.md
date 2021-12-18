# node . js util . types . iswakemap()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-iswakemap-method/](https://www.geeksforgeeks.org/node-js-util-types-isweakmap-method/)

**util . types . iswakmap()方法**是 **util** 模块的一个内置应用编程接口，主要是为了支持 **Node.js** 自身内部 API 的需求而设计的。

**util . types . iswakmap()方法**用于确定该值是否是内置的 **WeakMap** 实例。

**语法:**

```
util.types.isWeakMap( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**如果是内置 **WeakMap** 的实例，则返回布尔值，即返回 **true** ，否则返回 **false** 。

下面的例子说明了在 Node.js 中使用**util . types . iswakmap()方法**:

**例 1:**

```
// Node.js program to demonstrate the 
// util.types.isWeakMap() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isWeakMap() method
console.log(util.types.isWeakMap(true));

// Using util.types.isWeakMap() method
console.log(util.types.isWeakMap("map"));

// Using util.types.isWeakMap() method
console.log(util.types.isWeakMap(new WeakMap()));
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
// util.types.isWeakMap() method 

// Using require to access util module 
const util = require('util');

// Creating a Boolean Object
const a = new Boolean(true);

// Creating a Boolean Object
const b = new Boolean(false);

// A boolean type variable
const c = new WeakMap();

// Using util.types.isWeakMap() method
console.log(util.types.isWeakMap(a));

// Using util.types.isWeakMap() method
console.log(util.types.isWeakMap(b));

// Using util.types.isWeakMap() method
console.log(util.types.isWeakMap(c));
```

**输出:**

```
false
false
true
```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ iswakemap _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_isweakmap_value)