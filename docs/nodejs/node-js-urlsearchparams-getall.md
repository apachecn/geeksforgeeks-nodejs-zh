# node . js urlsearchparams . get all()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-getall/

在**urlsearchroprams**界面中， **getAll()** 方法以数组的形式返回输入搜索参数的所有值。

**语法:**

```
URLSearchParams.getAll(*name*)
```

**返回:**根据名称-值对的字符串数组，否则返回空数组。

**参数:**
**名称**–输入参数名称。

**示例 1:**

```
let url = new URL('https://example.com?par=5&bar=2'); 
let params = new URLSearchParams(url.search.slice(1)); 

//Add a second par parameter. 
params.append('par', 4);

console.log(params.getAll('par'))'
```

**输出:**

```
['5', '4']
```

**示例 2:** 当输入参数不存在时

```
let url = new URL('https://example.com?par=5&bar=2&bar=7&par=4&bar=9'); 
let params = new URLSearchParams(url.search.slice(1)); 

console.log(params.getAll('bar'))'
```

**输出:**

```
['2','7','9']
```

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari