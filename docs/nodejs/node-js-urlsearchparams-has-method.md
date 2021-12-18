# node . js urlsearchprams . has()方法

> 原文:[https://www . geesforgeks . org/node-js-urlsearchprams-has-method/](https://www.geeksforgeeks.org/node-js-urlsearchparams-has-method/)

在**urlsearchroprams**界面中， **has()** 方法返回一个*布尔*，告诉我们如果输入名称的参数存在，则返回 true，否则返回 false。

**语法:**

```
var Bool = URLSearchParams.has(*name*)
```

**返回:**真–如果名称存在，否则将返回假。

**参数:**
**名称**–输入参数名称。

**示例 1:**

```
let url = new URL('https://example.com?par=5&bar=4');
let param = new URLSearchParams(url.search.slice(1));

param.has('bar') === true; 
```

**输出:**

```
true
```

**示例 2:** 当输入参数不存在时

```
let url = new URL('https://example.com?par=5&bar=4');
let param = new URLSearchParams(url.search.slice(1));

param.has('foo') === true; 
```

**输出:**

```
false
```

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari