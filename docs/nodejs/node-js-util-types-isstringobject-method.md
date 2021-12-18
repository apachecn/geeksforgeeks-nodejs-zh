# node . js util . types . isstringobject()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isstringobject-method/](https://www.geeksforgeeks.org/node-js-util-types-isstringobject-method/)

util 模块的 **util.types.isStringObject()方法**主要是为了支持 Node.js 自己的内部 API 的需求而设计的。它用于检查方法中传递的实例是否是字符串对象。**字符串原语**和**字符串对象**是有区别的。在 javascript 中，字符串是一种原语数据类型，它没有方法，只是指向原始数据内存引用的指针。

**语法:**

```js
util.types.isStringObject( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何值，即任何模块的实例。

**返回值:**如果传递的值是字符串对象，该方法返回一个布尔值，即**真**，否则返回**假**。

下面的例子说明了 **util.types.isStringObject()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the    
// util.types.isStringObject() method 

// It includes util module 
const util = require('util'); 

// Return false as passed value is
// a string but not a String object 
console.log(util.types.isStringObject("geeksforgeeks")); 

// Return true as passed value is String object
console.log(util.types.isStringObject(new String())); 
```

**输出:**

```js
false
true
```

**例 2:**

```js
// Node.js program to demonstrate the    
// util.types.isStringObject() method 

// It includes util module 
const util = require('util'); 

//temp_string is a primitive datatype
var temp_string = "geeksforgeeks"

// Return false as passed value is a
// string but not a String object 
console.log(util.types.isStringObject(temp_string)); 

//making string into String object
var s_object = new String(temp_string);

// Return true as passed value is a string
// but not a String object 
console.log(util.types.isStringObject(s_object));

//Return false as passes value is not a String object
console.log(util.types.isStringObject(new Set()));
```

**输出:**

```js
false
true
false
```

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isstringobject _ value