# Node.js util.types.isRegExp()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isregexp-method/](https://www.geeksforgeeks.org/node-js-util-types-isregexp-method/)

util 模块的 **util.types.isRegExp()方法**，主要是为了支持 Node.js 自带的内部 API 的需求而设计的。用于检查传递的**值**是否为正则表达式。

**语法:**

```
util.types.isRegExp( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何值，即任何模块的实例。

**返回值:**如果传递的值是正则表达式，该方法返回一个布尔值，即**真**，否则返回**假**。

下面的例子说明了 **util.types.isRegExp()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the   
// util.types.isRegExp() method

// It includes util module
const util = require('util');

// Returns false as the passed instance
// is not regular expression
console.log(util.types.isRegExp(new Map()));

// Returns true as the passed instance
// is regular expression
console.log(util.types.isRegExp(new RegExp('xyz')));
```

**输出:**

```
false
true
```

**例 2:**

```
// Node.js program to demonstrate the   
// util.types.isRegExp() method

// It includes util module
const util = require('util');

// Returns false as the passed instance
// is not regular expression
console.log(util.types.isRegExp(new Map()));

// Returns true as the passed instance
// is regular expression
console.log(util.types.isRegExp(new RegExp('xyz')));

// Returns true as the passed instance
// is regular expression
console.log(util.types.isRegExp(/abc/));

// Returns false as the passed instance
// is not regular expression
console.log(util.types.isRegExp(new Int32Array()));

// Returns true as the passed instance
// is regular expression 
console.log(util.types.isRegExp(/ab+c/));
```

**输出:**

```
false
true
true
false
true
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isregexp _ value](https://nodejs.org/api/util.html#util_util_types_isregexp_value)