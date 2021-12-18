# node . js util . types . is generator function()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is generator function-method/](https://www.geeksforgeeks.org/node-js-util-types-isgeneratorfunction-method/)

**util . types . IsGeneratorFunction()方法**是 util 模块的内置应用编程接口，主要是为了支持 Node.js 自身内部 API 的需求而设计的。
使用**util . types . is generator function()方法**检查给定值是否是一个发生器函数。

**语法:**

```
util.types.isGeneratorFunction( value )
```

**参数:**该函数接受一个参数，如上所述，如下所述:

*   **值:**这是将为发电机功能检查的值。

**返回值:**如果传递的值是生成器函数，则返回布尔值，即**真**，否则返回**假**。

下面的程序说明了 Node.js 中的**util . types . is generator function()****方法**:

**例 1:**

## Node.js

```
// Node.js program to demonstrate the
// util.types.isGeneratorFunction() method

// Import the util module
const util = require('util');

// Getting the generator function
let GeneratorFunction = 
      Object.getPrototypeOf(function*(){}).constructor

// Checking the generator function
let genFn = new GeneratorFunction();
console.log(genFn);

isGenFn = util.types.isGeneratorFunction(genFn);
console.log("Object is a generator function:", isGenFn);

// Checking a normal function
let normalFn = function helloWorld() {};
console.log(normalFn);

isGenFn = util.types.isGeneratorFunction(normalFn);
console.log("Object is a generator function:", isGenFn);
```

**输出:**

```
[GeneratorFunction: anonymous]
Object is a generator function: true
[Function: helloWorld]
Object is a generator function: false
```

**例 2:**

## Node.js

```
// Node.js program to demonstrate the
// util.types.isGeneratorFunction() method

// Import the util module
const util = require('util');

// Checking a generator function
let genFn = function* getID() {
      let id = 0;
      while (true)
        yield id++;
};
console.log(genFn);

isGenFn = util.types.isGeneratorFunction(genFn);
console.log("Object is a generator function:", isGenFn);

// Checking a normal function
let normalFn = function helloGeeks() { 
      console.log("Hello World")
};

console.log(normalFn);

isGenFn = util.types.isGeneratorFunction(normalFn);
console.log("Object is a generator function:", isGenFn);
```

**输出:**

```
[GeneratorFunction: getID]
Object is a generator function: true
[Function: helloGeeks]
Object is a generator function: false

```

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isgenerator function _ value