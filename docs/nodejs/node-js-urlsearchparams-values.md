# node . js urlsearchprams . values()

> 原文:[https://www . geesforgeks . org/node-js-urlsearchprams-values/](https://www.geeksforgeeks.org/node-js-urlsearchparams-values/)

在**urlsearchroprams**界面中， **values()** 方法返回一个*迭代器*，它允许我们遍历对象中存在的所有值

**语法:**

```
searchParams.values();
```

**返回:**返回每个名称-值对的值的 ES6 迭代器。

**例 1:**

```
// Create a test URLSearchParams object
var searchParams = new URLSearchParams("keyA=valueA&keyB=valueB");

// Display the values
for(var value of searchParams.values()) {
  console.log(value);
}
```

**输出:**

```
valueA
valueB
```

**示例 2:** 直接创建参数

```
// Create a test URLSearchParams object
var searchParams = new URLSearchParams("name=deepak&age=18");

// Display the values
for(var value of searchParams.values()) {
  console.log(value);
}
```

**输出:**

```
deepak
18
```

**支持的浏览器:**

*   谷歌铬
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari