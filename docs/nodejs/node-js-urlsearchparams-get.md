# node . js urlsearchprams . get()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-get/

在**urlsearcheparams**界面中， **get()** 方法返回输入搜索参数的第一个值。

**语法:**

```
URLSearchParams.get(*name*)
```

**返回:**如果找到名称-值对，则返回字符串，否则返回 null。

**参数:**
**名称**–输入参数名称。

**示例 1:** 当输入参数存在时

```
var URL = require('url').URL;
let url = new URL('https://example.com/?name=Deepak&age=20');
let params = new URLSearchParams(url.search.substring(1));
let name = params.get("name"); // is the string "Deepak"
let age = parseInt(params.get("age"), 10); // is the number 20
console.log(name)
console.log(age)
```

**输出:**

```
Deepak
20
```

**示例 2:** 当输入参数不存在时

```
var URL = require('url').URL;
let url = new URL('https://example.com/?name=Deepak&age=20');
let params = new URLSearchParams(url.search.substring(1));
let address = params.get("address");
console.log(address)
```

**输出:**

```
null
```

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari