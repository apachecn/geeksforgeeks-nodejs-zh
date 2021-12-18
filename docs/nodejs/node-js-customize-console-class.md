# Node.js 自定义控制台类

> 原文:[https://www . geesforgeks . org/node-js-customize-console-class/](https://www.geeksforgeeks.org/node-js-customize-console-class/)

Console 类可用于创建具有可配置输出流的记录器，基本用法在 [Node.js 新 Console()方法](https://www.geeksforgeeks.org/node-js-new-console-method/)中描述。但是正如您可能观察到的，有些选项只允许布尔值作为输入。

例如，当您有各种输出数据时，启用**颜色模式**非常有用。Node.js 提供了一个非常方便的设置来显示控制台日志。但是，在某些情况下，您可能仍然希望在不安装任何附加软件包的情况下对其进行修改以满足您的需要。

在本文中，我们将首先介绍如何使用**控制台**类的一些其他高级设置的**检查选项**，然后解释如何修改**颜色模式**的细节。

**示例 1:** 使用默认控制台类。它展示数据的方式与全局控制台相同，即*控制台. log* 。

## index.js

```js
const { Console } = require('console');

const logger = new Console({
    stdout: process.stdout,
    stderr: process.stderr,
});

logger.log('log: object', {attr: 
    'string content a b c d e f g h i j k'});
logger.log('log: array', ['array_value1', 'array_value2', 
'array_value3', 'array_value4', 'array_value5']);
logger.log('log: set', new Set([3, 1, 2, 5, 4]));
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
log: object { attr: 'string content a b c d e f g h i j k' }
log: array [
  'array_value1',
  'array_value2',
  'array_value3',
  'array_value4',
  'array_value5'
]
log: set Set(5) { 3, 1, 2, 5, 4 }
```

**例 2:** 如果我们没有足够的空间来展示一切，希望它更短、更有条理。我们将在**检查选项**对象中指定以下属性，并将它们附加到控制台选项。

*   **maxArrayLength:** 用于指定格式化时要包含的数组元素的最大数量。默认值:100。
*   **maxStringLength:** 用于指定格式化时要包含的最大字符数。默认值:10000。
*   **排序:**如果设置为真，则使用默认排序，如果设置为函数，则用作比较函数。

## index.js

```js
const { Console } = require('console');

const logger = new Console({
    stdout: process.stdout,
    stderr: process.stderr,
    inspectOptions: {

        // Maximum number of Array elements 
        // to include when formatting.
        maxArrayLength: 3, 

        // Maximum number of characters to 
        // include when formatting.
        maxStringLength: 10, 

        // If properties of an object are sorted
        sorted: true,
    }
});

logger.log('log: object', {attr: 
        'string content a b c d e f g h i j k'});
logger.log('log: array', ['array_value1', 'array_value2', 
'array_value3', 'array_value4', 'array_value5']);
logger.log('log: set', new Set([3, 1, 2, 5, 4]));
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> 日志:对象{ attr:'字符串内容 a b c '……多 16 个字符}
> 日志:数组[ 'array_value1 '，' array_value2 '，array _ value3 '，…多 2 项]
> 日志:set Set(5) { 1，2，3，4，5 }

**说明:**如果你看一下**检查**接受的参数，有一个叫做**颜色**。该参数的优先级高于控制台类中的**颜色模式。如果设置了**检查颜色**，则忽略**颜色模式**。同样，它只允许布尔值。也就是说，它接受真或假。这可能令人失望，但如果一次只有一个记录器要处理，这里有一个解决方法。**

**示例 3:** 我们可以修改**中的默认设置，如下图示例代码所示。([这里](https://nodejs.org/api/util.html#util_customizing_util_inspect_colors)是每个数据类型可接受的所有值的列表)。请注意，这是一种修改全局配色方案的方法。应用更改后，启用颜色模式并遵循此配色方案的所有其他组件都会受到影响。**

## index.js

```js
const { Console } = require('console');
const util = require('util');

// This can be declared after the 
// logger is created, too.
util.inspect.styles.number = 'red';

const logger = new Console({
    stdout: process.stdout,
    stderr: process.stderr,
    inspectOptions: {

        // Remember to enable the color mode.
        // Default is false.
        colors: true
    }
});

// Now the number in the set are all shown in red.
logger.log('log: set', new Set([3, 1, 2, 5, 4]));
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

```js
log: set Set { 3, 1, 2, 5, 4 }
```

**参考:**[https://nodejs . org/API/util . html # util _ customizing _ util _ inspect _ colors](https://nodejs.org/api/util.html#util_customizing_util_inspect_colors)