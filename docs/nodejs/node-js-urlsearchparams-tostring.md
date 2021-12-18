# node . js urlsearchparams . tostring()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-tostring/

在**URL 搜索参数**界面中， *toString()* 方法返回一个适合在 URL 中使用的*查询字符串*。

**语法:**

```js
URLSearchParams.toString()
```

**返回:**返回序列化为字符串的搜索参数(字符百分比编码)。

**例 1:**

```js
let url = new URL('https://example.com?foo=1&bar=2');
let params = new URLSearchParams(url.search.slice(1));

//Add another parameter.
params.append('par', 4);
console.log(params.toString());
```

**输出:**

```js
'foo=1&bar=2&par=4'
```

**示例 2:** 直接创建参数

```js
// note: params can also be directly created
let url = new URL('https://example.com?par=1&bar=2');
let params1 = url.searchParams;
console.log(params1.toString());
// or even simpler
let params2 = new URLSearchParams('par=1&bar=2');
console.log(params2.toString());
```

**输出:**

```js
par=1&bar=2
par=1&bar=2
```

**支持的浏览器:**

*   谷歌铬
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari