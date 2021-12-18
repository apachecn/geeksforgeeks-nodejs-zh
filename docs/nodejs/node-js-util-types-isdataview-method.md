# node . js | util . types . isdata view()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-isdata view-method/](https://www.geeksforgeeks.org/node-js-util-types-isdataview-method/)

util 模块的 **util.types.isDataView()方法**方法主要是为了支持 Node.js 自身内部 API 的需求而设计的。
使用 **util.types.isDataView()方法**检查给定值是否为 DataView 对象。

**语法:**

```
util.types.isDataView(value)

```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **值:**是将为数据视图对象检查的值。

**返回值:**如果传递的值是数据视图的实例，该方法返回一个布尔值，即**真**，否则返回**假**。

下面的程序说明了 Node.js:
中的 **util.types.isDataView()方法**

**例 1:**

## Node.js

```
// Node.js program to demonstrate the    
// util.types.isDataView() method 

// Import the util module
const util = require('util');

// Checking for a DataView
let arraybuf = new ArrayBuffer(5);
let dataView = new DataView(arraybuf);
console.log("Value:", dataView);

isDataView = util.types.isDataView(dataView);
console.log("Value is a DataView:", isDataView);

// Checking for an Integer array
let intArray = new Int32Array();
console.log("Value:", intArray);

isDataView = util.types.isDataView(intArray);
console.log("Value is a DataView:", isDataView);
```

**输出:**

```
Value: DataView {
  byteLength: 5,
  byteOffset: 0,
  buffer: ArrayBuffer { [Uint8Contents]:
  <00 00 00 00 00>, byteLength: 5 }
}
Value is a DataView: true
Value: Int32Array []
Value is a DataView: false

```

**例 2:**

## Node.js

```
// Node.js program to demonstrate the    
// util.types.isDataView() method 

// Import the util module
const util = require('util');

// Creating an unsigned integer 8-bit array
let int8Array = new Uint8Array([10, 20, 30]);
console.log("Value:", int8Array);

// Checking for a view
console.log("Value is a View:", 
      ArrayBuffer.isView(int8Array));

// Checking for a DataView
isDataView = util.types.isDataView(int8Array);
console.log("Value is a DataView:", isDataView);

// Creating a dataview
let dataView = new DataView(new ArrayBuffer(3));
dataView.setUint8(0, 10);
dataView.setUint8(1, 20);
dataView.setUint8(2, 30);
console.log("Value:", dataView);

// Checking for a view
console.log("Value is a View:",
      ArrayBuffer.isView(dataView));

// Checking for a DataView
isDataView = util.types.isDataView(dataView);
console.log("Value is a DataView:", isDataView);
```

**输出:**

```
Value: Uint8Array [ 10, 20, 30 ]
Value is a View: true
Value is a DataView: false
Value: DataView {
  byteLength: 3,
  byteOffset: 0,
  buffer: ArrayBuffer { [Uint8Contents]: 
  <0a 14 1e>, byteLength: 3 }
}
Value is a View: true
Value is a DataView: true

```

**参考:**[https://nodejs . org/API/util . html # util _ util _ types _ isdataview _ value](https://nodejs.org/api/util.html#util_util_types_isdataview_value)