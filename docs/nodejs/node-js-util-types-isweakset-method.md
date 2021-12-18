# node . js util . types . iswakeset()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-iswakeset-method/](https://www.geeksforgeeks.org/node-js-util-types-isweakset-method/)

**util . types . iswakeset()方法**是 **util** 模块的内置应用编程接口，主要是为了支持 **Node.js** 自身内部 API 的需求而设计的。

**util . types . iswakeset()方法**用于确定该值是否是内置的 [WeakSet](https://www.geeksforgeeks.org/javascript-weakset/) 实例。

**语法:**

```
util.types.isWeakSet( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**如果是内置 **WeakSet** 的实例，则返回布尔值，即返回 **true** ，否则返回 **false** 。

下面的例子说明了**util . types . iswakeset()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the 
// util.types.isWeakSet() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isWeakSet() method
console.log(util.types.isWeakSet(true));

// Using util.types.isWeakSet() method
console.log(util.types.isWeakSet("set"));

// Using util.types.isWeakSet() method
console.log(util.types.isWeakSet(new WeakSet()));
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
// util.types.isWeakSet() method 

// Using require to access util module 
const util = require('util');

// Creating a WeakSet Object
const a = new WeakSet();

// Add values
a.add(new Boolean(true));

// Creating a WeakSet Object
const b = new WeakSet();

// Using util.types.isWeakSet() method
console.log(util.types.isWeakSet(a));

// Using util.types.isWeakSet() method
console.log(util.types.isWeakSet(b));
```

**输出:**

```
true
true

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ iswakeset _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_isweakset_value)