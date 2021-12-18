# node . js process . through defensation Property

> 原文:[https://www . geeksforgeeks . org/node-js-process-throwdeprivation-property/](https://www.geeksforgeeks.org/node-js-process-throwdeprecation-property/)

**process . throw-defense 属性**是流程模块的内置应用编程接口，用于指示当前 Node.js 流程是否设置了–throw-defense 标志。process.throwDeprecation 是可变的，因此在运行时，是否会因为拒绝警告而导致错误可能会改变。

**语法:**

```
process.throwDeprecation
```

**返回值:**该属性表示当前 Node.js 进程是否设置了–throw-defense 标志。

下面的例子说明了在 Node.js 中**进程的使用。**

**例 1:**

## Javascript

```
// Node.js program to demonstrate the
// process.throwDeprecation Property

// Include process module
const process = require('process');

// Printing process.throwDeprecation
// property value
console.log(process.throwDeprecation);
```

**运行命令:**节点–抛出-弃用 hello.js

**输出 1:**

```
true
```

**运行命令:**节点 hello.js

**输出 2:**

```
undefined
```

**例二:**

## Javascript

```
// Node.js program to demonstrate the
// process.throwDeprecation Property

// Include process module
const process = require('process');

// Instance Properties
process.throwDeprecation = false;

// Printing process.throwDeprecation
// property value
console.log(process.throwDeprecation);

// Instance Properties
process.throwDeprecation = true;

// Printing process.throwDeprecation
// property value
console.log(process.throwDeprecation);
```

**运行命令:**节点–抛出-弃用 hello.js

**输出 1:**

```
true
true
```

**运行命令:**节点 hello.js

**输出 2:**

```
false
true
```

**参考:**[https://nodejs . org/API/process . html # process _ process _ through desverage](https://nodejs.org/api/process.html#process_process_throwdeprecation)