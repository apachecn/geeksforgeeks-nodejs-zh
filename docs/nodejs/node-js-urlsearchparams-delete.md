# node . js urlsearchprams . delete()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-delete/

在**urlsearcheparams**界面中， **delete()** 方法删除用户指定的参数及其所有关联值。

**语法:**

```js
URLSearchParams.delete(*name*)
```

**参数:**
**名称**–要删除的参数名称。

**例 1:**

```js
let url = new URL('https://example.com?par=1&bar=2&par=3');
let params = new URLSearchParams(url.search.slice(1));

// Delete the par parameter.
params.delete('par');
console.log(url)
```

**输出:**

```js
https://example.com?bar=2
```

**例 2:**

```js
let url = new URL('https://example.com?foo=1&par=3');
let params = new URLSearchParams(url.search.slice(1));

// Delete the foo parameter.
params.delete('foo');
console.log(url)
```

**输出:**

```js
https://example.com?par=3
```

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari