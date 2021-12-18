# Node.js util.types.isMap()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-ismap-method/](https://www.geeksforgeeks.org/node-js-util-types-ismap-method/)

**util.types.isMap()方法**是 **util** 模块的内置应用编程接口，主要设计用于支持 **Node.js** 自身内部 API 的需求。

**util.types.isMap()方法**用于确定该值是否是内置的[地图](https://www.geeksforgeeks.org/map-in-javascript/)实例。

**语法:**

```js
util.types.isMap( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**返回布尔值，即如果值是内置地图的实例，则返回**真**，否则返回**假**。

下面的例子说明了 **util.types.isMap()方法**在 Node.js 中的使用:

**例 1:**

```js
// Node.js program to demonstrate the 
// util.types.isMap() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isMap() method
console.log(util.types.isMap(1));

// Using util.types.isMap() method
console.log(util.types.isMap("Map"));

// Using util.types.isMap() method
console.log(util.types.isMap(new Map()));
```

**输出:**

```js
false
false
true

```

**例 2:**

```js
// Node.js program to demonstrate the 
// util.types.isMap() method 

// Using require to access util module 
const util = require('util');

// Creating a Map variable
const map = new Map();

// Entering values in Map
map.set("geeks", "Computer science");

map.set("Hello", "World");

// Creating a String type variable
const text = "GeeksforGeeks";

// Using util.types.isMap() method
console.log(util.types.isMap(map));

// Using util.types.isMap() method
console.log(util.types.isMap(text));

// Using util.types.isMap() method
console.log(util.types.isMap());
```

**输出:**

```js
true
false
false

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ ismap _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_ismap_value)