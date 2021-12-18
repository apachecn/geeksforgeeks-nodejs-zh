# Django 和 Node.js 的区别

> 原文:[https://www . geesforgeks . org/difference-django-and-node-js/](https://www.geeksforgeeks.org/difference-between-django-and-node-js/)

在本文中，我们将了解 Django & Node.js，以及它们之间的区别。

[**Django:**](https://www.geeksforgeeks.org/django-tutorial/) 它是一个开源的基于 Python 的 web 框架，允许你创建 web 应用程序。Django 是由 2005 年建立的 Django 计划创建的，由**阿德里安·霍洛瓦蒂**和**西蒙·威廉森**策划。Django 最重要的部分是高级 python 网络框架，因为该系统提供了规划应用程序的完美方式。这是基于不要重复自己的指导方针。Django 是创建 web 应用程序或网站的不同 python 系统中最值得注意的级别类别。Django 在制作现代网络应用程序方面有着非凡的亮点和焦点。

作为一个设计师，应该遵循规则或方法来实现 Django 中的范围，与低级系统相比，灵活性相对较低，但是所做的应用程序将是完美和干净的。Django 主要采用名为[模型模板视图(MTV)](https://www.geeksforgeeks.org/django-project-mvt-structure/) 的平面设计。除了格式之外，它还与 [MVC 系统](https://www.geeksforgeeks.org/mvc-design-pattern/)相比较。像 MVC 一样，MTV 必须将信息传递到模型中的层。演示处理协作、关联信息或批准信息的方法。布局层被间接称为介绍层，它处理应该在互联网页面或应用程序上显示的内容。种子是交易层，因为它可以具体到模型，并显示合适的布局。

**姜戈特色:**

*   **Versatile:** Jiang Ge can build almost any type of website. It can also work with any client framework and deliver content in any format, such as HTML, JSON, XML, etc. Some websites that can be established by using Django include wikis, social networks, new websites and so on.
*   **Security:** Because Django framework is made to make network development easy, it is designed to automatically do the right thing to protect the website. For example, in the Django framework, instead of putting the password into cookies, the *hash password* is stored in them, so that hackers will not easily get it.
*   **Scalability:** Django web nodes have no storage state, they are horizontally scalable-just need to stimulate more when needed. Being able to do this is the essence of good scalability. Instagram and Disqus are two products based on Django.
*   **Portability:** All codes of Django framework are written in Python and run on many platforms. This led to Django running on many platforms, such as Linux, Windows and Mac OS.

**示例:**这是简单的 Django 程序。

## 蟒 3

```
#Variable store integer value
a = 35
print(type(a))

#Variable store string value
a = "GeeksforGeeks"
print(type(a))

#Variable store boolean value
a = True
print(type(a))

#Dictionary with the use of Mixed Keys
a = {'Name': 'Geeks', 1: [1, 2, 3, 4]}
print(type(a))
```

**输出:**

```
<class 'int'>
<class 'str'>
<class 'bool'>
<class 'dict'>
```

[**Node.js:**](https://www.geeksforgeeks.org/nodejs-tutorials/) Node.js 是一个开源的跨平台运行时环境，用于在浏览器外执行 [JavaScript](https://www.geeksforgeeks.org/javascript-tutorial/) 代码。它是由**瑞安达尔**在 2009 年开发的。它是用 C、C++和 JavaScript 编写的。换句话说，Node.js 可以是一个 JavaScript 平台，它的功能就像一个网络服务器，允许工程师利用 JavaScript 编写全面且非常通用的网络应用程序。Node.js 是基于谷歌 V8 JavaScript 引擎构建的。有成千上万的开源库来支持 NodeJS。你需要记住 NodeJS 不是一个框架，也不是一种编程语言。大多数人都很困惑，明白这是一个框架或者一种编程语言。我们经常使用 Node.js 来构建后端服务，比如像 Web App 或者移动 App 这样的 API。贝宝、优步、网飞、沃尔玛等大公司都在生产中使用它。

**NodeJS 的特点:**

*   Easy to use, can be used for prototype development and agile development.
*   Provide fast and highly scalable services.
*   For javascript programmers, it is easy to build back-end services with Node.js because it uses JavaScript.
*   The source code is cleaner and more consistent.
*   A huge open source library.
*   Have [asynchronous](https://www.geeksforgeeks.org/asynchronous-patterns-in-node-js/) or non-blocking properties.

**示例:**这是简单的 Node.js 程序。

## Javascript

```
// Variable store number data type
var a = 35;
console.log(typeof a);

// Variable store string data type
a = "GeeksforGeeks";
console.log(typeof a);

// Variable store Boolean data type
a = true;
console.log(typeof a);

// Variable store undefined (no value) data type
a = undefined;
console.log(typeof a);
```