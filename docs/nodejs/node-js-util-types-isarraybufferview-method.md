# node . js util . types . isarraybufferview()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isarraybufferview-method/](https://www.geeksforgeeks.org/node-js-util-types-isarraybufferview-method/)

“util”模块提供用于调试目的的“实用”功能。为了访问这些函数，我们需要调用它们(通过“require”(“util”))。

**util . types . isarraybufferview()**(在 v10.0.0 中添加)方法是 util 模块的内置应用编程接口，相当于 *ArrayBuffer.isView()* 方法。它检查该值是类型化数组对象之一的实例还是数据视图，即*数组填充器*视图。如果传递的值是类型化的*数组对象*或*数据视图*，即*数组缓冲区*，则返回“真”，否则返回“假”。

**语法:**

```js
const util = require('util');
util.types.isArrayBufferView(value);

```

**参数:**该方法接受如上所述的单个参数，如下所述:

*   **值** *<任意>* **:** 它是接受任意变量、类、函数、对象或 JavaScript 原语或任意数据类型的必需参数。

**返回值** *<布尔>* **:** 返回一个布尔值。如果传递的值是类型化的数组对象或数据视图，即 ArrayBuffer，则返回“真”，否则返回“假”。

下面的例子说明了在 Node.js 中 util.types.isArrayBufferView()方法的使用

**示例 1:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// util.types.isArrayBufferView() method 

// Using require to access util module 
const util = require('util'); 
const {types} = require('util'); 

// Passing ArrayBuffer as parameter
console.log("1.>", util.types.isArrayBufferView(new ArrayBuffer()));  
// Returns false

// Passing Array with argument as parameter
console.log("2.>", util.types.isArrayBufferView([1, "a", "@", "18"]));  
// Returns false

// Passing Buffer as parameter
console.log("3.>", 
util.types.isArrayBufferView(Buffer.from('hello world'))); 
// Returns true

// Passing Float64Array as parameter
console.log("4.>", util.types.isArrayBufferView(new Float64Array()));  
// Returns true

// Passing data as parameter
console.log("5.>", util.types.isArrayBufferView([1, 5, 8, 18]));  
// Returns false

// Passing Array Buffer wrapped in dataView as parameter
console.log("6.>", 
util.types.isArrayBufferView(new DataView(new ArrayBuffer(16))));  
// Returns true

// Passing Int8Array as parameter
console.log("7.>", util.types.isArrayBufferView(new Int8Array(8)));  
// Returns true
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

> 1.>假
> 
> 2.>假
> 
> 3.>真
> 
> 4.>真
> 
> 5.>假
> 
> 6.>真
> 
> 7.>真

**示例 2:** **文件名:index.js**

```js
// Node.js program to demonstrate the 
// util.types.isArrayBufferView() method 

// Using require to access util module 
const util = require('util'); 
const {types} = require('util'); 

let value1 = Uint8Array.from([1, 2, 3, 4])
var akash = value1.subarray(0, 2)
var arrayBuffer = akash.buffer; 
var geeksforgeeks = new BigUint64Array(465);

// Passing converted arrayBuffer as parameter
console.log("1.>", util.types.isArrayBufferView(arrayBuffer));  
// Returns false

// Passing empty parameter
console.log("2.>", util.types.isArrayBufferView());  
// Returns false

// Passing Float32Array as parameter
console.log("3.>", util.types.isArrayBufferView(new Float32Array()));  
// Returns true

// Passing JSON as parameter
console.log("4.>", 
util.types.isArrayBufferView({name:"satyam", value:"sahai"}));  
// Returns false

var amit = new Uint8Array(["alfa", 1]);

// Converting to Array buffer
var newArrayBuffer = amit.buffer; 

// Converting and passing array buffer as parameter
console.log("5.>", util.types.isArrayBufferView(newArrayBuffer));  
// Returns false

// Passing Uint8Array as parameter
console.log("6.>", types.isArrayBufferView(new Uint8Array()));  
// Returns true

// Passing and converting buffer as parameter
console.log("7.>", types.isArrayBufferView(geeksforgeeks.buffer));  
// Returns false

var var1 = new ArrayBuffer(); 
var var2 = new Int16Array(); 

// Calling util.types.isArrayBufferView() method 
if (util.types.isArrayBufferView(var1)) 
    console.log("Yes, the value have ArrayBuffer View."); 
else
    console.log("No, provided value do not have ArrayBuffer View."); 

// Calling util.types.isArrayBufferView() method 
if (util.types.isArrayBufferView(var2)) 
    console.log("Yes, the value have ArrayBuffer View."); 
else
    console.log("No, provided value do not have ArrayBuffer View"); 
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

> 1.>假
> 
> 2.>假
> 
> 3.>真
> 
> 4.>假
> 
> 5.>假
> 
> 6.>真
> 
> 7.>假
> 
> 否，提供的值没有数组填充视图。
> 
> 是的，该值有数组填充视图。

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isarraybbuffer view _ value](https://nodejs.org/api/util.html#util_util_types_isarraybufferview_value)