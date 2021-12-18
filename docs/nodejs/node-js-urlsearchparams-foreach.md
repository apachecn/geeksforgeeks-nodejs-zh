# node . js urlsearchprams . foreach()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-foreach/

在 **URLSearchParams** 界面中， **foreach()** 方法返回一个迭代器，该迭代器允许在回调函数的帮助下遍历该对象中包含的所有值。

**语法:**

```
searchParams.forEach(*callback*);
```

**Return:** 它不返回任何东西，用于调用函数和迭代函数。

**参数:**
**回调**–输入将针对每个参数执行的回调函数，所提供的参数值作为其参数。

**示例 1:**

```
// Create a test URLSearchParams object
const myURL = new URL('https://example.org/?keya=vala&keyb=valb');

// Log the values
myURL.searchParams.forEach(function(value, key) {
  console.log(value, key);
});
```

**输出:**

```
vala keya
valb keyb
```

**示例 2:**

```
// Create a test URLSearchParams object
const myURL = new URL('https://example.org/?par=parval&foo=fooval&bar=barval');

// Log the values
myURL.searchParams.forEach(function(value, key) {
  console.log(key,value);
});
```

**输出:**

```
par parval
foo fooval
bar barval
```

**支持的浏览器:**

*   谷歌 Chrome
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari