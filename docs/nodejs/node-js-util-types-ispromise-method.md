# node . js util . types . isclose()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is problese-method/](https://www.geeksforgeeks.org/node-js-util-types-ispromise-method/)

**util . types . isclosee()方法**是 **util** 模块的内置应用编程接口，主要是为了支持 **Node.js** 自身内部 API 的需求而设计的。

**util . typesconvery()方法**用于确定该值是否为内置的**承诺**。

**语法:**

```js
util.types.isPromise( value )
```

**参数:**该方法接受单个参数**值**，该值保存任何有效的 JavaScript 数据类型，如布尔、空、数字、对象等。

**返回值:**返回布尔值，即如果值是内置的**承诺**则返回**真**，否则返回**假**。

下面的例子说明了在 Node.js 中使用**util . types . iscomproise()方法**:

**例 1:**

```js
// Node.js program to demonstrate the 
// util.types.isPromise() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isPromise() method
console.log(util.types.isPromise(true));

// Using util.types.isPromise() method
console.log(util.types.isPromise(new Set()));

// Using util.types.isPromise() method
console.log(util.types.isPromise(
    new Promise(function(resolve, reject){})));
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
// util.types.isPromise() method 

// Using require to access util module 
const util = require('util');

// Using util.types.isPromise() method
console.log(util.types.isPromise(true));

// Using util.types.isPromise() method
console.log(util.types.isPromise(new Set()));

// Defining a Promise
var promise = new Promise(function(resolve, reject) { 
    const x = "geeksforgeeks"; 
    const y = "geeksforgeeks"
    if(x === y) { 
        resolve(); 
    } else { 
        reject(); 
    } 
}); 

// Using util.types.isPromise() method
console.log(util.types.isPromise(promise. 
    then(function () { 
        console.log('Success, You are a GEEK'); 
    }). 
    catch(function () { 
        console.log('Some error has occured'); 
    })
));
```

**输出:**

```js
false
false
true
Success, You are a GEEK

```

**注意:**以上程序使用`node index.js`命令编译运行。

**参考:**[https://nodejs . org/dist/latest-v 13 . x/docs/API/util . html # util _ util _ types _ is promise _ value](https://nodejs.org/dist/latest-v13.x/docs/api/util.html#util_util_types_ispromise_value)