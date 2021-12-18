# node . js process . tracedevention 属性

> 原文:[https://www . geesforgeks . org/node-js-process-trace defense-property/](https://www.geeksforgeeks.org/node-js-process-tracedeprecation-property/)

**process . TraceDerection 属性**是流程模块的内置应用编程接口，用于指示当前 Node.js 流程是否设置了–TraceDerection 标志。

**语法:**

```
process.traceDeprecation
```

**返回值:**该属性表示当前 Node.js 进程是否设置了–trace-defense 标志。

下面的例子说明了在 Node.js 中使用 process.traceDeprecation 属性:

**例 1:**

## index.js

```
// Node.js program to demonstrate the
// process.traceDeprecation Property

// Include process module
const process = require('process');

// Printing process.traceDeprecation property value
console.log(process.traceDeprecation);
```

使用以下命令运行 **index.js** 文件:

```
node --trace-deprecation index.js
```

**输出:**

```
true
```

再次运行相同的文件，但使用不同的命令，如下所示:

```
node index.js
```

**输出:**

```
undefined
```

**例 2:**

**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// process.traceDeprecation Property

// Include process module
const process = require('process');

// Instance Properties 
process.traceDeprecation = false;

// Printing process.traceDeprecation
// property value
console.log(process.traceDeprecation);

// Instance Properties 
process.traceDeprecation = true;

// Printing process.traceDeprecation
// property value
console.log(process.traceDeprecation);
```

使用以下命令运行 **index.js** 文件:

```
node --trace-deprecation index.js
```

**输出:**

```
true
true
```

再次运行相同的文件，但使用不同的命令，如下所示:

```
node index.js
```

**输出:**

```
false
true
```