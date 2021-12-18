# node . js urlsearchprams . keys()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-urlsearchparams-keys/

在**urlsearchroprams**界面中， **keys()** 方法返回一个*迭代器*，它允许我们遍历对象中存在的所有键。

**语法:**

```jshtml
searchParams.keys();
```

**返回:**返回每个名称-值对名称的 ES6 迭代器。

**例 1:**

```jshtml
var searchParams = new URLSearchParams("keyA=valueA&keyB=valueB"); 

// Display the key/value pairs 
for(var key of searchParams.keys()) { 
  console.log(key); 
}
```

**输出:**

```jshtml
keyA
keyB
```

**范例 2:**

```jshtml
var searchParams = new URLSearchParams("name=john&age=18"); 

// Display the key/value pairs 
for(var key of searchParams.keys()) { 
  console.log(key); 
}
```

**输出:**

```jshtml
name
age
```

**支持的浏览器:**

*   谷歌铬
*   工业管理学(Industrial Engineering)
*   边缘
*   歌剧
*   苹果 Safari