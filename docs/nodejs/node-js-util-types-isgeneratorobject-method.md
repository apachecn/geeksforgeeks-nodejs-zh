# node . js util . types . is generatorobject()方法

> 原文:[https://www . geesforgeks . org/node-js-util-types-is generatorobject-method/](https://www.geeksforgeeks.org/node-js-util-types-isgeneratorobject-method/)

**util . types . IsGeneratorObject()方法**是 util 模块的内置应用编程接口，主要是为了支持 Node.js 自身内部 API 的需求而设计的。
使用**util . types . is generatorobject()方法**检查给定值是否为生成器对象。

**语法:**

```
util.types.isGeneratorObject( value )
```

**参数:**该函数接受单个参数**值**，该值保存将为生成器对象检查的值。

**返回值:**如果传递的值是生成器对象，则返回布尔值，即**真**，否则返回**假**。

下面的程序说明了 Node.js 中的**util . types . is generatorobject()方法**:

**例 1:**

```
// Node.js program to demonstrate the
// util.types.isGeneratorObject() method

// Import the util module
const util = require('util');

// Creating a generator function
let GeneratorFunction = 
    Object.getPrototypeOf(function*(){}).constructor

let genFn = new GeneratorFunction();

// Checking the generator object
let genObj = genFn();
console.log(genObj);

isGenObj = util.types.isGeneratorObject(genObj);
console.log("Object is a generator object:", isGenObj);

// Checking a normal object
normalObj = {a: "1", b: "2"};
console.log(normalObj);

isGenObj = util.types.isGeneratorObject(normalObj);
console.log("Object is a generator object:", isGenObj);
```

**输出:**

```
Object [Generator] {}
Object is a generator object: true
{ a: '1', b: '2' }
Object is a generator object: false
```

**例 2:**

```
// Node.js program to demonstrate the
// util.types.isGeneratorObject() method

// Import the util module
const util = require('util');

// Creating a generator function
let genFn = function* generateNumber() {
    let id = 0;

    while (true)
        yield id++;
};

// Checking the generator object
let genObj = genFn();
console.log(genObj);

isGenObj = util.types.isGeneratorObject(genObj);
console.log("Object is a generator object:", isGenObj);

// Checking a normal object
normalObj = {arg1: "1", arg2: "2"};
console.log(normalObj);

isGenObj = util.types.isGeneratorObject(normalObj);
console.log("Object is a generator object:", isGenObj);
```

**输出:**

```
Object [Generator] {}
Object is a generator object: true
{ arg1: '1', arg2: '2' }
Object is a generator object: false
```

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ types _ isgenerator object _ value