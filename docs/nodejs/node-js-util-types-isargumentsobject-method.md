# node . js | util . types . isargumentobject()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isargumentobject-method/](https://www.geeksforgeeks.org/node-js-util-types-isargumentsobject-method/)

**util . types . isargumentobject()方法**是 util 模块的内置应用编程接口，主要是为了支持 Node.js 自身内部 API 的需求而设计的。
util . types . isargumentobject()方法用于检查给定值是否是参数对象。

**语法:**

```
util.types.isArgumentsObject( value )

```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **值:**是要为参数对象检查的值。

**返回值:**如果传递的值是参数对象，则返回布尔值，即**真**，否则返回**假**。

下面的程序说明了 Node.js:
中的**util . types . isargumentobject()方法**

**例 1:**

## Node.js

```
// Node.js program to demonstrate the
// util.types.isArgumentsObject() method

// Import the util module
const util = require('util');

// Checking the arguments object
console.log(util.types.isArgumentsObject(arguments));

// Checking new object created by the constructor
console.log(util.types.isArgumentsObject(new Object()));

// Checking a normal object
console.log(util.types.isArgumentsObject(
            {arg1: "Hello", arg2: "World"}));
```

**输出:**

```
true
false
false

```

**例 2:**

## Node.js

```
// Node.js program to demonstrate the
// util.types.isArgumentsObject() method

// Import the util module
const util = require('util');

function exampleFn(arg1, arg2) {

  // Checking the arguments object
  let argumentsObj = arguments;
  console.log(arguments);

  isArgumentObj = util.types.isArgumentsObject(argumentsObj);
  console.log("Object is arguments object:", isArgumentObj);

  // Checking a normal object
  let normalObj = {arg1: "hello", arg2: "world"};
  console.log(normalObj);

  isArgumentObj = util.types.isArgumentsObject(normalObj);
  console.log("Object is arguments object:", isArgumentObj);
}

exampleFn('hello', 'world');
```

**输出:**

```
[Arguments] { '0': 'hello', '1': 'world' }
Object is arguments object: true
{ arg1: 'hello', arg2: 'world' }
Object is arguments object: false

```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isaarguments subject _ value](https://nodejs.org/api/util.html#util_util_types_isargumentsobject_value)