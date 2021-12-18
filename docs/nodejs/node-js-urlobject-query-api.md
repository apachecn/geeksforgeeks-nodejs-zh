# node . js urlobject . query API

> 原文:[https://www.geeksforgeeks.org/node-js-urlobject-query-api/](https://www.geeksforgeeks.org/node-js-urlobject-query-api/)

urlObject.query 是返回的查询字符串，不带 ASCII 问号(？)或名为 parse()方法的 querystring 模块返回的对象。Url.parse()方法用于检查查询是字符串还是对象。基本上，传递给 url.parse()方法的参数(parseQueryString)告诉查询的性质。

**语法**

```
urlObject.query
```

**注意:**如果这个方法返回一个字符串，那么不执行对查询字符串的解码，如果它返回一个对象，那么两个键、值对都被解码。

**例:**

```
'query=string' or {'query': 'object'}

'http://localhost:8000/gfg.html?name:GFG'
In the above URL, the name is the query and GFG is the string.

```

下面的程序说明了在 Node.js 中 **url.query** 方法的使用:

**例 1:**

```
// Node program to demonstrate the  
// url.query API as Setter

// Importing the module 'url'
var url = require('url');

// Set the URL from which the queryString will be fetched
var address = 'http://localhost:8000/gfg.html?month=Decemeber'; 

// Parse the address
var q = url.parse(address, true);

// The query property returns an object with all the
// querystring parameters as properties
var query = q.query;

var month = query.month;

console.log(month);
```

**输出:**

```
December
```

**例 2:**

```
// Node program to demonstrate the  
// url.query API as Setter

// Importing the module 'url'
var url = require('url');

// Set the URL from which the queryString will be fetched
var address = 'http://localhost:8000/gfg.html?month=Decemeber&year=2019'; 

// Parse the address
var q = url.parse(address, true);

// The query property returns an object with all the
// querystring parameters as properties
var query = q.query;

var year = query.year;

console.log(year);
```

**输出:**

```
2019
```

**参考:**[https://nodejs . org/API/URL . html # URL _ URL object _ query](https://nodejs.org/api/url.html#url_urlobject_query)