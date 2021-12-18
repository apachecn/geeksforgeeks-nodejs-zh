# Node.js util.inspect()方法

> 原文:[https://www.geeksforgeeks.org/node-js-util-inspect-method/](https://www.geeksforgeeks.org/node-js-util-inspect-method/)

“util”模块提供用于调试目的的“实用”功能。为了访问这些函数，我们需要通过“require”(“util”)”来调用它们。

util.inspect()(在 v0.3.0 中添加)方法是 util 模块的内置应用程序编程接口，用于调试并返回对象的字符串表示形式。util.inspect()方法不依赖于编程。它返回可能随时改变的输出，以改变可以传递的结果补充选项(如显示隐藏、深度)。对于已检查的值，要么使用构造函数名称，要么使用 *@@toStringTag* 作为可识别的标记。

**语法:**

```js
const util = require('util');
util.inspect(object[, options])
```

**参数:**该函数接受两个参数，如上所述，如下所述:

*   **对象** <任意> **:** 任意类、函数、对象或 JavaScript 原语。

*   **选项** *<对象>* **:** 选项为“对象”类型，接受数据的 JSON 形式。

    *   **显示隐藏的** *<布尔>* **:** 默认情况下，对象的值设置为“假”，如果设置为“真”，则它开始在格式化结果中显示隐藏的不可枚举符号和属性以及用户定义的原型、WeakMap 和 WeakSet 条目。
    *   **深度** *<号>* **:** 默认情况下，对象的值设置为‘2’。它指定递归的次数，并且在检查大对象和调用堆栈大小时，传递*无穷大*或*空值*以递归到最大值。
    *   **颜色** *<布尔>* **:** 默认情况下，对象的值设置为“假”，如果设置为“真”，则输出获得带有 ANSI 颜色代码的彩色样式。
    *   **自定义检查** *<布尔>* **:** 默认情况下，对象的值设置为“真”，如果设置为“假”，则不调用[[util.inspect.custom](深度，opts)]函数。
    *   **显示代理** *<布尔>* **:** 默认情况下，对象的值设置为“假”，如果设置为“真”，则代理检查包括目标和处理程序对象。
    *   **maxArrayLength***<integer>***:默认情况下，对象的值设置为‘100’。格式化时，指定最大长度，即格式化结果中需要包含多少个数组、WeakMaps 和 WeakSets。若要不显示(0)元素，请将该值设置为 0 或负值，若要显示所有元素，请将该值设置为无穷大或 null。**
    *   **maxStringLength***<integer>***:**默认情况下，对象的值设置为‘Infinity’。格式化时，指定最大字符长度，即格式化结果中包含的字符长度。若要不显示(")字符，请将该值设置为 0 或负值，若要显示所有元素，请将该值设置为无穷大或 null。
    *   **隔断长度** *<整数>* **:** 默认情况下，对象的值设置为‘80’。格式化时，它指定了输入值跨多行拆分的最大长度。要将输入格式化为单行，请将其设置为无穷大。
    *   **排序** *<布尔> | <函数>* **:** 默认情况下，对象的值设置为“假”，如果设置为“真”或传递了一个函数，则所有属性都在格式化字符串中排序。如果设置为“真”，则使用默认排序；如果设置为函数，则用作比较函数。
    *   **吸气器** *<布尔> | <字符串>* **:默认情况下，对象的值设置为“假”，如果设置为“真”，那么吸气器将被检查。如果设置为“获取”，则只检查吸气剂。如果设置为“设置”，则只检查带有相应设置器的吸气剂。这种副作用的风险很高，取决于吸气功能。**

**返回值:** *<字符串>* **:** 返回表示对象的格式化字符串。

**示例 1:** **文件名:index.js**

```js
// Node.js syntax to demonstrate
// the util.inspect() method 

// Importing util library
const util = require('util');

// Object
const nestedObject = {};
nestedObject.a = [nestedObject];
nestedObject.b = [['a', ['b']], 'b', 'c', 'd'];
nestedObject.b = {};
nestedObject.b.inner = nestedObject.b;
nestedObject.b.obj = nestedObject;

// Inspect by basic method
console.log("1.>", util.inspect(nestedObject));

// Random class 
class geeksForGeeks { }

// Inspecting geeksForGeeks class 
console.log("2.>", util.inspect(new geeksForGeeks()));

// Inspect by passing options to method
console.log("3.>", util.inspect(
        nestedObject, true, 0, false));

// Inspect by calling option name
console.log("4.>", util.inspect(nestedObject,
    showHidden = false, depth = 0, colorize = true));

// Inspect by passing in JSON format 
console.log("5.>", util.inspect(nestedObject,
    { showHidden: false, depth: 0, colorize: true }));

// Inspect by directly calling inspect from 'util'
const { inspect } = require('util');

// Directly calling inspect method
// with single property
console.log("6.>", inspect(nestedObject),
        { colorize: true });

// Directly passing the JSON data
console.log("7.>", util.inspect([
    { name: "Amit", city: "Ayodhya" },
    { name: "Satyam", city: "Lucknow" },
    { name: "Sahai", city: "Lucknow" }],
    false, 3, true));

// Directly calling inspect method with single property
console.log("8.>", inspect(nestedObject), { depth: 0 });
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

```js
1.> <ref *1> {
  a: [ [Circular *1] ],
  b: <ref *2> { inner: [Circular *2], obj: [Circular *1] }
}
2.> geeksForGeeks {}
3.> { a: [Array], b: [Object] }
4.> { a: [Array], b: [Object] }
5.> { a: [Array], b: [Object] }
6.> <ref *1> {
  a: [ [Circular *1] ],
  b: <ref *2> { inner: [Circular *2], obj: [Circular *1] }
} { colorize: true }
7.> [
  { name: 'Amit', city: 'Ayodhya' },
  { name: 'Satyam', city: 'Lucknow' },
  { name: 'Sahai', city: 'Lucknow' }
]
8.> <ref *1> {
  a: [ [Circular *1] ],
  b: <ref *2> { inner: [Circular *2], obj: [Circular *1] }
} { depth: 0 }

```

**示例 2:** **文件名:index.js**

```js
// Node.js syntax to demonstrate the 
// util.inspect() method 

// Import the util module 
const util = require('util');
const { inspect } = require('util');

// Importing http module
var http = require('http');

// Inspecting http module
console.log("1.>", util.inspect(http, {
    showHidden: false,
    depth: 0, showProxy: false
}));

// Inspecting console module
console.log("2.>", util.inspect(
    console, showHidden = false,
    depth = 0, showProxy = true));

// Creating array filled with default value 1
const inspectArray = Array(108).fill(1);

// Prints the truncated array
console.log("3.>", inspectArray);
util.inspect.defaultOptions.maxArrayLength = null;

// Prints the full array
console.log("4.>", inspectArray);

const object = {
    amit: [1, 2, [[
        'alfa_romeo, spp___, sahai_harshit ' +
        'Annapurna, chai paratha.',
        'chota',
        'bong']], 55],
    vikas: new Map([
        ['alfa', 1], ['romeo', 'data']])
};

// Returns the compact view output.
console.log("5.>", util.inspect(object, {
    compact: true, depth: 5,
    breakLength: 80
}));

// Returns the output more reader friendly.
console.log("6.>", util.inspect(object, {
    compact: false, depth: 5,
    breakLength: 80
}));

const object1 = { alfa: 10 };
const object2 = { beta: 20 };

// Creating weakSet
const inspectingWeakset = 
    new WeakSet([object1, object2]);

console.log("7.>", inspect(
    inspectingWeakset, { showHidden: true }));
// Output { { alfa: 10 }, { beta: 20 } }

object2[util.inspect.custom] = (depth) => {
    return { alfaa: 'romeo' };
};

console.log("8.>", util.inspect(object2));
// Prints: "{ alfaa: 'romeo' }"
```

使用以下命令运行 **index.js** 文件:

```js
node index.js

```

**输出:**

> 1.> { _ connectionListener:[函数:connectionListener]，…。全局代理:[Getter/Setter]}
> 2。> {日志:[功能:绑定控制台全部]，…..[符号(kformafostderr)]【功能:绑定】}
> 3。>【1、1、1、1、1、1、……1、1、1、1、1、……8 更多项目】
> 4。>【1，1，1，1，1，1，1，1，1，1，1，1，…1，1，1，1，1，1，1，1，1，1，1，1，1，1，1，1】
> 5。> { amit: [ 1，2，[ 'alfa_romeo，spp__，sahai_harshit Annapurna，chai paratha . '，
> 'chota '，' bong' ]，55 ]，vikas: Map(2) { 'alfa' = > 1，' Romeo ' =>' data ' }
> 6。> ***返回的输出更加读者友好。***
> 7。> WeakSet { { alfa: 10 }，{ beta: 20 } }
> 8。> {阿尔法:《罗密欧》}

[*util.format(format[，…])*](https://www.geeksforgeeks.org/node-js-util-format-method/) 方法也使用第一个参数作为类似 printf 的格式给出了与格式化字符串相同的结果。

**参考:**[https://nodejs . org/API/util . html # util _ util _ inspect _ object _ options](https://nodejs.org/api/util.html#util_util_inspect_object_options)