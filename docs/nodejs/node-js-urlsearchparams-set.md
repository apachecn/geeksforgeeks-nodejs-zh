# node . js urlsearchprams . set()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-set/

在 **URLSearchParams** 界面中， **set()** 方法将给出的值设置为输入参数。如果有几个值与输入参数匹配，则删除其他值，如果该值不存在，则创建它。

**语法:**

```
URLSearchParams.set(*name*, *value*)
```

**参数:**
**名称**–输入参数名称。
**值**–输入参数值。

**例 1:**

```
let url = new URL('https://example.com?fo=4&bar=6');
let params = new URLSearchParams(url.search.slice(1));

//Add another parameter.
params.set('par', 5);
console.log(params.toString());
```

**输出:**

```
fo=4&bar=6&par=5
```

**示例 2:** 添加多个参数

```
let url = new URL('https://example.com?a=1&b=2');
let params = new URLSearchParams(url.search.slice(1));

//Add another parameter.
params.set('c', 3);
params.set('d', 4);
console.log(params.toString());
```

**输出:**

```
a=1&b=2&c=3&d=4
```

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari