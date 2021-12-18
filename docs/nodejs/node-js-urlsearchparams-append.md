# node . js urlsearchprams . append()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-append/

在 **URLSearchParams** 界面中， **append()** 方法添加用户指定的键/值对。
**语法:**

```
URLSearchParams.append(*name*, *value*)
```

**参数:**
**名称**–输入要追加的参数名称
**值**–输入要追加的参数值

**示例 1:**

```
let url = new URL('https://example.com?par=1&par1=3');
let params = new URLSearchParams(url.search.slice(1));

//Add a second par parameter.
params.append('bar', 5);
console.log(url);
```

**输出:**

```
https://example.com?par=1&par1=3&bar=5
```

**示例 2:**

```
let url = new URL('https://example.com?par=1');
let params = new URLSearchParams(url.search.slice(1));

//Add a second par parameter.
params.append('bar', 2);
console.log(url);
```

**输出:**

```
https://example.com?par=1&bar=2
```

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari