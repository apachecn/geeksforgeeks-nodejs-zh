# Node.js util.types.isSet()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isset-method/](https://www.geeksforgeeks.org/node-js-util-types-isset-method/)

util 模块的 **util.types.isSet()方法**主要是为了支持 Node.js 自带的内部 API 的需求而设计的。它用于检查方法中传递的实例是否是内置的 Set 实例。

**语法:**

```
util.types.isSet( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何值，即任何模块的实例。

**返回值:**如果传递的值是 Set 的内置实例，该方法返回一个布尔值，即**真**，否则返回**假**。

下面的例子说明了 **util.types.isSet()方法**在 Node.js 中的使用:

**例 1:**

```
// Node.js program to demonstrate the    
// util.types.isSet() method 

// It includes util module 
const util = require('util'); 

// Return true as passed instance is of Set
console.log(util.types.isSet(new Set())); 

// Return false as passed instance is of Map
console.log(util.types.isSet(new Map())); 
```

**输出:**

```
true
false
```

**例 2:**

```
// Node.js program to demonstrate the    
// util.types.isSet() method 

// It includes util module 
const util = require('util'); 

// Making a set object of a string
var set1 = new Set("geeksforgeeks");

// Return true as passed instance is of Set
console.log(util.types.isSet(set1));

const numbers = [2, 3, 4, 4, 2, 3, 3, 4,
       4, 5, 5, 6, 6, 7, 5, 32, 3, 4, 5];

// Making a set object of array
var set2 = new Set(numbers);

// Return true as passed instance is of Set
console.log(util.types.isSet(set2)); 

// Return false as passed instance is of Map
console.log(util.types.isSet(new Map())); 
```

**输出:**

```
true
true
false
```

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isset _ value