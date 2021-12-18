# Node.js util.format()方法

> 原文:[https://www.geeksforgeeks.org/node-js-util-format-method/](https://www.geeksforgeeks.org/node-js-util-format-method/)

**util.format()** (在 v0.5.3 中添加)方法是 util 模块的内置应用编程接口，类似于 *printf* 格式字符串，并使用第一个参数返回格式化字符串。格式化字符串包含零个或多个格式说明符，在这些说明符中，相应的参数值被转换和替换。它被用作调试工具，是一种同步方法，因此，它可能会有很大的性能开销，可能会阻塞事件循环。建议不要在热代码路径中使用此函数。

**语法:**

```
util.format(format[, ...args])
```

**参数:**该方法接受两个参数，如上所述，如下所述:

**格式:**由 *<字符串>* 类型的说明符组成，类似于 *printf* 格式字符串。

**args:** 它是 *<串>* 类型的参数列表。

**支持的说明符有:**

*   **%:**它将说明符替换为单个百分号( *'%%'* / *'%'* )，即使它提供了参数，也不会消耗任何参数。
*   **%s** ( *字符串* ) **:** 它根据给定的格式转换除*对象*、 *BigInt* 和 *-0* 以外的所有值。*没有自定义*到字符串*功能的对象*使用***util . inspect()***和 *BigInt* 值用 *n* 表示。
*   **%c** ( *CSS* ) **:** 如果有 *CSS* 通过，则跳过。通常，该说明符被忽略。
*   **%d** ( *数字* ) **:** 除了*符号*和 *BigInt* 之外，它根据给定的格式转换所有的值。
*   **% I**(*parsent()*)**:**解析一个<字符串>返回一个整数，用于除 *BigInt* 和*符号*以外的所有值。
*   **% f**(*parseFloat()*)**:**它解析一个字符串并返回一个浮点数，它用于除*符号*以外的所有值。
*   **% j**(*JSON*)**:**没有复杂的解析或翻译，如果参数中有循环引用，则用字符串“[循环]”替换。
*   **%o** ( *对象* ) **:** 它是带有通用 JavaScript 对象格式的*对象的字符串表示。类似于 *util.inspect()* 。它显示了完整的对象以及不可枚举的属性和代理。*
*   **%O** ( *对象* ) **:** 类似于 *'%o'* ，但没有选项，不包含*不可枚举的*属性和代理。

**返回值:**返回<字符串>类型的格式化字符串。

**示例 1:**
**文件名:index.js**

## java 描述语言

```
// Node.js to demonstrate the
// util.format() method 

// Import the util module 
const util = require('util');

function fun1() {
    var val1 = util.format('%s:%s:%s', 'abc');
    // Returns: 'foo:%s'

    var val2 = util.format('%s:%s', 
        'abc', 'def', 'ghi', 'jkl');
    // Returns: 'foo:bar baz'

    var val3 = util.format(10, 20, 30);
    // Returns: '1 2 3'

    var val4 = util.format('%% : %s : %d');
    // Returns: '%% %s'

    var val5 = util.format('%% : %s', 567);
    // Returns: '% : 567'

    console.log(val1, '\n', val2, '\n', 
        val3, '\n', val4, '\n', val5);
}

// Function call
fun1(); 
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
abc:
:abc:def ghi jkl
10 20 30
%% : %s : %d
% : 567
```

**示例 2:**
**文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate
// the util.format() method 

// Import the util module 
const util = require('util');

// Passing multiple values and
// -0 on string specifier
console.log("1.>", util.format(
    '%%: %s', 'abc', 'def', -0));

// Passing multiple values 
console.log("2.>", util.format(
    '%%', 'abc', 'def', 'ghi'));

// Passing bigInt to string specifier
console.log("3.>", util.format('%s', 
    'abc', 94321321321223372036854775807));

// Creating and passing Object along 
// with null prototype and a variable
console.log("4.>", util.format('%s', 
        'abc', Object.create(null,
        { [Symbol.toStringTag]: 
            { value: 'def' } })));

// Passing string to Number specifier
console.log("5.>", util.format('%d', 
            'abc', 94303685));

// Passing Symbol and Number to
// parseInt specifier
console.log("6.>", util.format(
    '%i', '2020 year 2021, ', 'He was 40,'
    , '10.33, ', '10, ', 10));

// Passing string and Numbers
// to parseFloat specifier
console.log("7.>", util.format('%f', 
    '94321321321.564000 year 6546',
    'abc', 943036854775807));

// Passing JSON string and Number
// to JSON specifier
console.log("8.>", util.format('%j',
    '{ "name":"John", "age":31, "city":"New York" }', 
    'abc', 943036854775807));

// Passing class, string, and Number
// to object specifier
console.log("9.>", util.format('%o', 
    class Bar { }, 'abc', 943036854775807));

// Passing class, string, and Number
// to Object specifier
console.log("10.>", util.format('%o:%d',
    class Foo { get [Symbol.toStringTag]() 
        { return 'abc'; } },
        'abc',
        943036854775807
));

// Random class
class randomClass { }

// Inspecting random class
console.log("11.>", 
    util.inspect(new randomClass()));
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

```
1.> %: abc def -0
2.> % abc def ghi
3.> abc 9.432132132122338e+28
4.> abc [Object: null prototype] [def] {}
5.> NaN 94303685
6.> 2020 He was 40, 10.33, 10, 10
7.> 94321321321.564 abc 943036854775807
8.> "{ \"name\":\"John\", \"age\":31, 
    \"city\":\"New York\" }" abc 943036854775807
9.> <ref *1> [Function: Bar] {
    [length]: 0,
    [prototype]: Bar { [constructor]: [Circular *1] },
    [name]: 'Bar'
   } abc 943036854775807
10.> <ref *1> [Function: Foo] {
    [length]: 0,
    [prototype]: Foo {
    [constructor]: [Circular *1],
    [Symbol(Symbol.toStringTag)]: [Getter]
    },
    [name]: 'Foo'
   }:NaN 943036854775807
11.> randomClass {}
```

**条件:**

*   如果没有相应的参数传递给说明符，则不会替换它。
*   如果传递的多个参数多于说明符的数量，那么额外的参数将被连接到返回的字符串。
*   如果“值”不属于格式字符串，并且其类型不是字符串，则使用 *util.inspect()* 方法格式化它们。
*   如果第一个参数没有有效的格式说明符，则 *util.format()* 返回串联的参数。

**参考:**T2】https://nodejs . org/API/util . html # util _ util _ format _ args