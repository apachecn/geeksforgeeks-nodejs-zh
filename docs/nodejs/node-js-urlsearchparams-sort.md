# node . js urlsearchprams . sort()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-sort/

在 **URLSearchParams** 界面中， *sort()* 方法有助于对所有键/对进行适当的排序。排序标准是键的 unicode 点。该方法采用稳定的排序算法。

**语法:**

```js
searchParams.sort();
```

**返回:**按名称对现有名称-值对进行就地排序。

**范例 1:**

```js
// Create a test URLSearchParams object 
var searchPars = new URLSearchParams("d=4&c=2&b=3&a=1"); 

// Sort the key/value pairs
searchPars.sort();

// Display the sorted query string
console.log(searchPars.toString());
```

**输出:**

```js
a=1&b=3&c=2&d=4
```

**范例 2:**

```js
// Create a test URLSearchParams object 
var searchPars = new URLSearchParams("z=4&a=2&t=3&a=1"); 

// Sort the key/value pairs
searchPars.sort();

// Display the sorted query string
console.log(searchPars.toString());
```

**输出:**

```js
a=2&a=1&t=3&z=4
```

**支持的浏览器:**

*   谷歌铬
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari