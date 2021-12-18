# Node.js querystring.parse()方法

> 原文:[https://www . geesforgeks . org/node-js-query string-parse-method/](https://www.geeksforgeeks.org/node-js-querystring-parse-method/)

**querystring.parse()方法**用于将一个网址查询字符串解析为一个对象，该对象包含查询网址的键值和对值。返回的对象没有从 JavaScript 对象继承原型，因此通常的对象方法不起作用。在解析过程中，除非有替代的字符编码格式，否则将采用 UTF-8 编码格式。要解码替代字符编码，必须指定 decodeURIComponent 选项。

**语法:**

```js
querystring.parse( str[, sep[, eq[, options]]]) )

```

**参数:**该功能接受四个参数，如上所述，描述如下:

*   **字符串:**它是一个字符串，指定必须解析的网址查询。
*   **sep:** 它是一个 String，指定用于分隔指定查询字符串中的键和值对的子字符串。默认值为“&”。
*   **eq:** 它是一个 String，指定用于分隔指定查询字符串中的键和值的子字符串。默认值为“=”。
*   **选项:**是可以用来修改方法行为的对象。它具有以下参数:
    *   **decodeURIComponent:** 这是一个用于解码查询字符串中百分比编码字符的函数。默认值为 querystring.unescape()。
    *   **maxKeys:** 它是一个数字，指定应该从查询字符串中解析的最大键数。值“0”将删除所有计数限制。默认值为“1000”。

**返回值:**它返回一个对象，该对象具有从查询字符串中解析的键和值对。

下面的例子说明了 Node.js 中的 **querystring.parse()** 方法:

**例 1:**

## Node.js

```js
// Import the querystring module
const querystring = require("querystring");

// Specify the URL query string
// to be parsed
let urlQuery = 
  "username=user1&units=kgs&units=pounds&permission=false";

// Use the parse() method on the string
let parsedObject = querystring.parse(urlQuery);

console.log("Parsed Query:", parsedObject);

// Use the parse() method on the string
// with sep as `&&` and eq as `-`
urlQuery = 
  "username-user1&&units-kgs&&units-pounds&&permission-false";
parsedObject = querystring.parse(urlQuery, "&&", "-");

console.log("\nParsed Query:", parsedObject);
```

**输出:**

```js
Parsed Query: [Object: null prototype] {
  username: 'user1',
  units: [ 'kgs', 'pounds' ],
  permission: 'false'
}

Parsed Query: [Object: null prototype] {
  username: 'user1',
  units: [ 'kgs', 'pounds' ],
  permission: 'false'
}

```

**例 2:**

## Node.js

```js
// Import the querystring module
const querystring = require("querystring");

// Specify the URL query string
// to be parsed
let urlQuery = 
  "user=admin&articles=1&articles=2&articles=3&access=true";

// Use the parse() method on the string
// with default values
let parsedObject = querystring.parse(urlQuery, "&", "=");

console.log("Parsed Query:", parsedObject);

// Use the parse() method on the string
// with maxKeys set to 1
parsedObject = 
  querystring.parse(urlQuery, "&", "=", { maxKeys: 1 });

console.log("\nParsed Query:", parsedObject);

// Use the parse() method on the string
// with maxKeys set to 2
parsedObject = 
  querystring.parse(urlQuery, "&", "=", { maxKeys: 2 });

console.log("\nParsed Query:", parsedObject);

// Use the parse() method on the string
// with maxKeys set to 0 (no limits)
parsedObject = 
  querystring.parse(urlQuery, "&", "=", { maxKeys: 0 });

console.log("\nParsed Query:", parsedObject);
```

**输出:**

```js
Parsed Query: [Object: null prototype] {
  user: 'admin',
  articles: [ '1', '2', '3' ],
  access: 'true'
}

Parsed Query: [Object: null prototype] { user: 'admin' }

Parsed Query: [Object: null prototype] 
              { user: 'admin', articles: '1' }

Parsed Query: [Object: null prototype] {
  user: 'admin',
  articles: [ '1', '2', '3' ],
  access: 'true'
}

```

**参考:**[https://nodejs . org/API/query string . html # query string _ query string _ parse _ str _ sep _ eq _ options](https://nodejs.org/api/querystring.html#querystring_querystring_parse_str_sep_eq_options)