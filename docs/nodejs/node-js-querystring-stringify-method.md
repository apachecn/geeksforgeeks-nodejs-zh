# node . js query string . stringify()方法

> 原文:[https://www . geesforgeks . org/node-js-query string-stringify-method/](https://www.geeksforgeeks.org/node-js-querystring-stringify-method/)

**querystring.stringify()方法**用于从包含键值对的给定对象中生成一个网址查询字符串。方法迭代对象自身的属性以生成查询字符串。

它可以序列化字符串、数字和布尔值的单个或数组。任何其他类型的值都被强制为空字符串。

在序列化过程中，UTF-8 编码格式用于编码任何需要百分制编码的字符。要使用替代字符编码进行编码，必须指定`encodeURIComponent`选项。

**语法:**

```
querystring.stringify( obj[, sep[, eq[, options]]] )
```

**参数:**该功能接受四个参数，如上所述，描述如下:

*   **obj:** 它是一个必须序列化为 URL 查询字符串的对象。
*   **sep:** 它是一个 String，指定用于分隔查询字符串中键和值对的子字符串。默认值为“&”。
*   **eq:** 它是一个 String，指定用于分隔查询字符串中的键和值的子字符串。默认值为“=”。
*   **选项:**它是一个可用于修改方法行为的对象。它具有以下参数:
    *   **encodeURIComponent:** 这是一个函数，用于将查询字符串中的 URL 不安全字符转换为百分比编码。默认值为`querystring.escape()`。

**返回值:**它返回一个字符串，该字符串包含从给定对象生成的网址查询。

下面的程序说明了 Node.js 中的 **querystring.stringify()** 方法:

**例 1:**

```
// Import the querystring module
const querystring = require("querystring");

// Specify the URL object
// to be serialized
let urlObject = {
    user: "sam",
    access: true,
    role: ["admin", "editor", "manager"],
};

// Use the stringify() method on the object
let parsedQuery = querystring.stringify(urlObject);

console.log("Parsed Query:", parsedQuery);
```

**输出:**

```
Parsed Query: user=sam&access=true&role=admin&role=editor&role=manager
```

**例 2:**

```
// Import the querystring module
const querystring = require("querystring");

// Specify the URL object
// to be serialized
let urlObject = {
    user: "max",
    access: false,
    role: ["editor", "manager"],
};

// Use the stringify() method on the object
// with sep as `, ` and eq as `:`
let parsedQuery = querystring.stringify(urlObject, ", ", ":");

console.log("Parsed Query 1:", parsedQuery);

// Use the stringify() method on the object
// with sep as `&&&` and eq as `==`
parsedQuery = querystring.stringify(urlObject, "&&&", "==");

console.log("\nParsed Query 2:", parsedQuery);
```

**输出:**

```
Parsed Query 1: user:max, access:false, role:editor, role:manager

Parsed Query 2: user==max&&&access==false&&&role==editor&&&role==manager
```

**参考:**[https://nodejs . org/API/query string . html # query string _ query string _ stringify _ obj _ sep _ eq _ options](https://nodejs.org/api/querystring.html#querystring_querystring_stringify_obj_sep_eq_options)