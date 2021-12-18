# node . js util . formatwithoptions()方法

> 原文:[https://www . geesforgeks . org/node-js-util-formatwwithtoptions-method/](https://www.geeksforgeeks.org/node-js-util-formatwithoptions-method/)

**util.formatWithOptions()** (在 v10.0.0 中添加)方法是 util 模块的内置应用编程接口，类似于 *printf* 格式字符串，并使用第一个参数返回格式化字符串。它与 [util.format()](https://www.geeksforgeeks.org/node-js-util-format-method/) 方法有些相同，但该方法的例外是它需要一个额外的参数，即*检查选项*，指定传递给 [util.inspect()方法](https://www.geeksforgeeks.org/node-js-util-inspect-method/)的选项。
格式化字符串包含零个或多个格式说明符，其中相应的参数值被转换和替换。它用作调试工具是一种同步方法。

**语法:**

```
util.formatWithOptions(inspectOptions, format[, ...args])
```

要使用这个函数，我们必须导入 util 模块:

```
const util=require("util");   
```

**参数:**该方法接受三个参数，如上所述，如下所述:

*   **督察组** < *对象* > **:接受函数、对象、回调、JSON 格式数据等。**
*   **格式** < *字符串* > **:** 由<字符串>类型的说明符组成，类似于 *printf* 格式字符串。
*   **args**<*string*>**:**它接受< *string* >类型的列表或参数数组。

**返回值** < *字符串* > **:** 返回< *字符串* >类型的格式化字符串。

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js to demonstrate the
// util.formatWithOptions() method

// Import the util module
const util = require('util');

function fun1() {

    // Returns: See object: {alfa:42}
    var val0 = util.formatWithOptions(
        { depth:0, colors: true },
        'See object %O', { alfa: 42 });

    // Returns: 'abc:%s'
    var val1 = util.formatWithOptions(
        { colors: true, showProxy : true },
        '%s:%s:%s', 'abc');

    // Returns: 'abc:def ghi'
    var val2 = util.formatWithOptions(
        { showHidden: true, colors: true },
        '%s:%s', 'abc', 'def', 'ghi', 'jkl');

    // Returns: '10 20 30'
    var val3 = util.formatWithOptions(
        { breakLength: 80, colors: true },
        10, 20, 30);

    // Returns: '% : 567'
    var val5 = util.formatWithOptions(
        { compact: true }, '%% : %s', 567);

    // Printing all values
    console.log(val0, '\n', val1, '\n',
        val2, '\n', val3, '\n', val5);
}

// Function call
fun1();
```

**输出:**

```
See object { alfa: 42 } 
abc:%s:%s 
abc:def ghi jkl        
10 20 30 
% : 567
```

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the
// util.formatWithOptions() method

// Import the util module
const util = require('util');

// Passing multiple values and
// -0 on string specifier
console.log("1 => ", util.formatWithOptions(
    { colors: true },
    '%%: %s', 'alfa', 'beta', -0));

// Passing multiple values
console.log("2 => ", util.formatWithOptions(
    { colors: true },
    '%%', 'alfa', 'beta', 'gamma'));

// Passing bigInt to string specifier
console.log("3 => ", util.formatWithOptions(
    { colors: true }, '%s',
    'alfa', 94321321321223372036854775807));

// Creating and passing Object along
// with null prototype and a variable
console.log("4 => ", util.formatWithOptions(
    {
        showHidden: false, depth: 0,
        colors: true
    }, '%s', 'alfa', Object.create(null,
    { [Symbol.toStringTag]: { value: 'beta' } })));

// Passing string to Number specifier
console.log("5 => ", util.formatWithOptions(
    { colors: true }, '%d', 'alfa',
    94303685));

// Passing Symbol and Number to parseInt specifier
console.log("6 => ", util.formatWithOptions(
    { showHidden: false, colors: true },
    '%i', '2020 year 2021, ', 'He was 40, ',
    '10.33, ', '10, ', 10));

// Passing string and Numbers to
// parseFloat specifier
console.log("7 => ", util.formatWithOptions(
    { colors: true }, '%f',
    '94321321321.564000 year 6546',
    'alfa', 78987965465464));

// Passing JSON string and Number
// to JSON specifier
console.log("8 => ", util.formatWithOptions(
    { depth: 0, colors: true }, '%j',
    '{ "name":"Chotu Mishra", "age":23, "city":"Kanpur" }',
    'alfa', 78987965465464));

// Passing class, string, and Number
// to object specifier
console.log("9 => ", util.formatWithOptions(
    { colors: true }, '%o',
    class Bar { }, 'alfa', 78987965465464));

// Passing class, string, and Number
// to Object specifier
console.log("10 => ", util.formatWithOptions(
    { depth: 0, colors: true }, '%o:%d',
    class Foo { get [Symbol.toStringTag]()
        { return 'alfa'; } }, 'alfa',
    78987965465464));
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
1 =>  %: alfa beta -0
2 =>  % alfa beta gamma
3 =>  alfa 9.432132132122338e+28
4 =>  alfa [Object: null prototype] [beta] {}
5 =>  NaN 94303685
6 =>  2020 He was 40,  10.33,  10,  10
7 =>  94321321321.564 alfa 78987965465464
8 =>  "{ \"name\":\"Chotu Mishra\", \"age\":23, 
      \"city\":\"Kanpur\" }" alfa 78987965465464
9 =>  [Function: Bar] {
  [length]: 0,
  [prototype]: Bar { [constructor]: [Circular] },
  [name]: 'Bar'
} alfa 78987965465464
10 =>  [Function: Foo] {
  [length]: 0,
  [prototype]: Foo {
    [constructor]: [Circular],
    [Symbol(Symbol.toStringTag)]: [Getter]
  },
  [name]: 'Foo'
}:NaN 78987965465464
```

**参考:**[https://nodejs . org/API/util . html # util _ util _ format withoptions _ inspection options _ format _ args](https://nodejs.org/api/util.html#util_util_formatwithoptions_inspectoptions_format_args)