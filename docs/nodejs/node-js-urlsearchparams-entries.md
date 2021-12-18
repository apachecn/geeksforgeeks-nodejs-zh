# node . js urlsearchprams . entries()

> 原文:[https://www . geesforgeks . org/node-js-urlsearchprams-entries/](https://www.geeksforgeeks.org/node-js-urlsearchparams-entries/)

在 **URLSearchParams** 界面中， **entries()** 方法返回一个迭代器，该迭代器允许遍历对象中存在的所有键/值对。键/值是 *USVString* 对象。

**语法:**

```js
searchParams.entries();
```

**返回:**迭代器，迭代所有键值对。

**例 1:**

```js
// Create a test URLSearchParams object
var searchpar = new URLSearchParams("keya=vala&keyb=valb");

// Display the key/value pairs
for(var pair of searchpar.entries()) {
   console.log(pair[0]+ ', '+ pair[1]); 
}
```

**输出:**

```js
keya, vala
keyb, valb
```

**例 2:**

```js
// Create a test URLSearchParams object
var searchpar = new URLSearchParams("par=parval&foo=fooval&bar=barval");

// Display the key/value pairs
for(var pair of searchpar.entries()) {
   console.log(pair[0]+ ', '+ pair[1]); 
}
```

**输出:**

```js
par, parval
foo, fooval
bar, barval
```

**支持的浏览器:**

*   谷歌铬
*   工业管理学(Industrial Engineering)
*   边缘(*部分*)
*   歌剧
*   苹果 Safari