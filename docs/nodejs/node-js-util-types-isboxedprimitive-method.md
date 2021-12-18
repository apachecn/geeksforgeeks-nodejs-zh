# node . js util . types . isboxedprimitive()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is box edprimitive-method/](https://www.geeksforgeeks.org/node-js-util-types-isboxedprimitive-method/)

**util.types.isBoxedPrimitive()方法**是 **util** 模块的内置应用编程接口，主要设计用于支持 Node.js 自身内部 API 的需求。

**util.types.isBoxedPrimitive()方法**用于检查给定值是否为装箱的图元。

**语法:**

```js
util.types.isBoxedPrimitive( value )
```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **Value:** It is the value of the packing element to be checked.

**返回值:**如果传递的值是装箱的图元，则返回布尔值，即**真**，否则返回**假**。

下面的例子说明了 Node.js 中的 **util.types.isBoxedPrimitive()方法**:

**例 1:**

```js
// Node.js program to demonstrate the    
// util.types.isBoxedPrimitive() method

// Import the util module
const util = require('util');

// Checking an unboxed string
let unboxedString = "GeeksforGeeks";
console.log("Value:", unboxedString);
isBoxed = util.types.isBoxedPrimitive(unboxedString);
console.log("Value is a boxed primitive:", isBoxed);

// Checking a boxed string
let boxedString = new String("GeeksforGeeks");
console.log("Value:", boxedString);
isBoxed = util.types.isBoxedPrimitive(boxedString);
console.log("Value is a boxed primitive:", isBoxed);

// Checking an unboxed integer
let unboxedInteger = 99;
console.log("Value:", unboxedInteger);
isBoxed = util.types.isBoxedPrimitive(unboxedInteger);
console.log("Value is a boxed primitive:", isBoxed);

// Checking a boxed integer
let boxedInt = new Number(99);
console.log("Value:", boxedInt);
isBoxed = util.types.isBoxedPrimitive(boxedInt);
console.log("Value is a boxed primitive:", isBoxed);

// Checking an unboxed boolean
let unboxedBool = false;
console.log("Value:", unboxedBool);
isBoxed = util.types.isBoxedPrimitive(unboxedBool);
console.log("Value is a boxed primitive:", isBoxed);

// Checking a boxed boolean
let boxedBool = new Boolean(false);
console.log("Value:", boxedBool);
isBoxed = util.types.isBoxedPrimitive(boxedBool);
console.log("Value is a boxed primitive:", isBoxed);
```

**输出:**

```js
Value: GeeksforGeeks
Value is a boxed primitive: false
Value: [String: 'GeeksforGeeks']
Value is a boxed primitive: true
Value: 99
Value is a boxed primitive: false
Value: [Number: 99]
Value is a boxed primitive: true
Value: false
Value is a boxed primitive: false
Value: [Boolean: false]
Value is a boxed primitive: true
```

**例 2:**

```js
// Node.js program to demonstrate the    
// util.types.isBoxedPrimitive() method

// Import the util module
const util = require('util');

// Checking for the symbol primitive
let symbol = Symbol('geeks');
console.log("Value:", symbol);
isBoxed = util.types.isBoxedPrimitive(symbol);
console.log("Value is a boxed primitive:", isBoxed);

// Checking again after creating a symbol wrapper
let symbolObj = new Object(Symbol('geeks'));
console.log("Value:", symbolObj);
isBoxed = util.types.isBoxedPrimitive(symbolObj);
console.log("Value is a boxed primitive:", isBoxed);
```

```js
Value: Symbol(geeks)
Value is a boxed primitive: false
Value: [Symbol: Symbol(geeks)]
Value is a boxed primitive: true
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isboxedprimitive _ value](https://nodejs.org/api/util.html#util_util_types_isboxedprimitive_value)