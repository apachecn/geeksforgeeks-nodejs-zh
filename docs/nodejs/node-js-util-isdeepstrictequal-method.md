# node . js util . isdeepstrictequal()方法

> 原文:[https://www . geesforgeks . org/node-js-util-isdeepstrictequal-method/](https://www.geeksforgeeks.org/node-js-util-isdeepstrictequal-method/)

“util”模块提供用于调试目的的“实用”功能。为了访问这些函数，我们需要调用它们(通过'*require(' util '*')。

**util.isDeepStrictEqual()** (在 v9.0.0 中添加)方法是 util 模块的内置应用程序编程接口，它是一个导出的类型函数，用于测试两个值的深度相等性，即实际(*值 1* )和预期(*值 2* )参数之间的相等性。深度相等是一种有助于通过一些规则递归地评估子对象的可枚举“拥有”属性的方法。

**语法:**

```
const util = require('util');
util.isDeepStrictEqual(val1, val2);
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **val 1***<Any>***:**Any 变量、类、函数、对象或 JavaScript 原语。

*   **val 2***<Any>***:**Any 变量、类、函数、对象或 JavaScript 原语。

**返回值** *<布尔>* **:** 如果认为值 1 和值 2 相等，则返回*真*，否则返回*假*。

**示例 1:** **文件名:index.js**

```

// Node.js syntax to demonstrate the 
// util.isDeepStrictEqual() method

// Importing util library
const util = require('util');

// Creating object1
const object1 = {
    alfa: "beta",
    romeo: [10, 20]
};

// Creating object2
const object2 = {
    alfa: "beta",
    romeo: [10, 20]
};

// Returns false
console.log("1.>", object1 == object2)

// Returns true
console.log("2.>", util
    .isDeepStrictEqual(object1, object2))

// Creating a fake date
const wrongDateType = {};

// Comparing wrongDateType with correct date
console.log("3.>", util.isDeepStrictEqual(
            wrongDateType, Date.prototype));

const anObject = {};

// Prototype is not same
console.log("4.>", util.isDeepStrictEqual(
            anObject, wrongDateType));
// Returns false

// Creating new date
const newDate = new Date();

// Comparing Date formats
console.log("5.>", util.isDeepStrictEqual(
            newDate, wrongDateType));
// Returns false

const weakMapOne = new WeakMap();
const weakMapTwo = new WeakMap([[{}, {}]]);

// Comparing two weakMaps  
console.log("6.>", util.isDeepStrictEqual(
            weakMapOne, weakMapTwo));
// Returns true
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
5.> false
6.> true

```

**示例 2:** **文件名:index.js**

```
// Node.js syntax to demonstrate the
// util.isDeepStrictEqual() method

// Importing util library
const util = require('util');

// String and integer are compared
// wrong 1 !== '1'.
console.log("1.>", util
    .isDeepStrictEqual({ a: 1 }, { a: '1' }));
// Returns false 

// Comparing Not a Number with Not a Number
console.log("2.>", util.isDeepStrictEqual(NaN, NaN));
// Returns true

// Unwrapped numbers are different
console.log("3.>", util
    .isDeepStrictEqual(Object(1), Object(2)));
// Returns false

// Directly importing isDeepStrictEqual method
const { isDeepStrictEqual } = require('util');

// Unwrapped strings are same
console.log("4.>", isDeepStrictEqual(
        Object('alfa'), Object('alfa')));
// Returns true

// Comparing both negative values  
console.log("5.>", isDeepStrictEqual(-0, -0));
// Returns true

// Same Value Comparison with different sign
console.log("6.>", isDeepStrictEqual(0, -0));
// Returns false
```

使用以下命令运行 **index.js** 文件:

```
node index.js

```

**输出:**

```
1.> false
2.> true
3.> false
4.> true
5.> true
6.> false

```

**参考:**[https://nodejs . org/API/util . html # util _ util _ isdeepstrictly equal _ val 1 _ val 2](https://nodejs.org/api/util.html#util_util_isdeepstrictequal_val1_val2)