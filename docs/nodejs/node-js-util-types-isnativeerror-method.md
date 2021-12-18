# node . js util . types . isnationerror()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is initiative error-method/](https://www.geeksforgeeks.org/node-js-util-types-isnativeerror-method/)

**util . types . isnationerror()**(在 v10.0.0 中添加)方法是 util 模块的内置应用程序编程接口，用于识别该值是否是 node.js 中内置 Error 类型的实例。如果该实例具有内置的“Error”，则返回“true”，否则返回“false”。

**语法:**

```
util.types.isNativeError( value )
```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **值** <任意> **:** 它是接受任何变量、类、函数、对象或 JavaScript 原语或任何数据类型的必需参数。

**返回** <布尔值> **:** 这将返回一个布尔值，如果实例具有内置的“错误”，则返回“真”，否则返回“假”。

下面的例子说明了在 Node.js 中使用*util . types . isnationerror(value)*方法

**示例 1:** **文件名:index.js**

```
// Node.js program to demonstrate the    
// util.types.isNativeError() Method

// Import the util module 
const util = require('util');
const {types} = require('util');

// Passing no values => Returns false
console.log("1.>", util.types.isNativeError());  

// Passing new inbuilt Error => Returns true
console.log("2.>", util.types.isNativeError(new Error())); 

// Passing new inbuilt TypeError => Returns true
console.log("3.>", util.types.isNativeError(new TypeError())); 

// Passing new inbuilt Error => Returns true
console.log("4.>", types.isNativeError(new RangeError())); 

// Passing new inbuilt Error => Returns true
console.log("5.>", util.types.isNativeError(new SyntaxError()));

// Passing new inbuilt Error => Returns true
console.log("6.>", types.isNativeError(new ReferenceError()));  
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
1.> false
2.> true
3.> true
4.> true
5.> true
6.> true

```

**示例 2:** **文件名:**

```
// Node.js program to demonstrate the    
// util.types.isNativeError() Method

// Import the util module 
const util = require('util');
const {types} = require('util');

// Directly importing and calling types
console.log("1.>", types.isNativeError(new Error("ksdjfhks")));

// Passing data/values directly
console.log("2.>", util.types.isNativeError(1234+'45'));  

// Passing Error.stack directly
console.log("3.>", util.types.isNativeError(Error.stack));  

// Passing util.types.isNativeError() method directly
console.log("4.>", 
util.types.isNativeError(util.types.isNativeError(new Error())));

// Passing util.types.isNativeError() method with 'Error'
console.log("5.>", 
util.types.isNativeError(util.types.isNativeError(Error)));

// Creating object
const object1 = {};
Error.captureStackTrace(object1);

// Passing object
console.log("6.>", util.types.isNativeError(object1.stack)); 

// Passing Error.captureStackTrace(object1)
console.log("7.>", 
util.types.isNativeError(Error.captureStackTrace(object1))); 

// Passing util.types.isNativeError() method with
/// nested error message
console.log("8.>", 
util.types.isNativeError(util.types.isNativeError(new Error())));

// Creating new error
const errorr = new Error('Some Error message');

// Passing new Error indirectly 
console.log("9.>", util.types.isNativeError(errorr)); 

// Passing error message 
console.log("10.>", util.types.isNativeError(errorr.message)); 

// Printing error
console.log("11.>", util.types.isNativeError(
        console.error(errorr.message))); 
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
1.> true
2.> false
3.> false
4.> false
5.> false
6.> false
7.> false
8.> false
9.> true
10.> false
Some Error message
11.> false

```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isnationerror _ value](https://nodejs.org/api/util.html#util_util_types_isnativeerror_value)