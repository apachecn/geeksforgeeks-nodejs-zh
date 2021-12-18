# 节点 url.toString()方法

> 原文:[https://www.geeksforgeeks.org/node-url-tostring-method/](https://www.geeksforgeeks.org/node-url-tostring-method/)

方法是**节点内网址模块的一个内置应用编程接口。JS** 。方法用于返回序列化的网址。返回值相当于 **url.href** 和 **url.toJSON()** 的值。

**语法:**

```
url.toString()
```

**参数:**该方法接受如上所述的单个参数，描述如下:

*   **url:** is an object created by the URL constructor.

**例 1:**

```
// Creating an URL object with URL constructor. 
const url = new URL("https://www.geeksforgeeks.org"); 

// Using toString() method 
console.log(url.toString()); 
```

**输出:**

```
https://www.geeksforgeeks.org

```

**例 2:**

```
// Creating an URL object with URL constructor. 
const url = new URL("https://www.google.com?foo=bar"); 

// Using toString() method 
console.log(url.toString()); 
```

**输出:**

```
https://www.google.com/?foo=bar

```

**参考:**[https://nodejs . org/API/URL . html # URL _ URL _ tostring](https://nodejs.org/api/url.html#url_url_tostring)