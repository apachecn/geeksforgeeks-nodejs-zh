# Node.js URL()方法

> 原文:[https://www.geeksforgeeks.org/node-js-url-method/](https://www.geeksforgeeks.org/node-js-url-method/)

“url”模块为 URL 解析和解析提供实用程序。getters 和 setters 在类原型上实现 URL 对象的属性，URL 类在全局对象上可用。

**新 URL()** ( *新增于 v7.0.0，v6.13.0* ) 方法是 URL 模块的内置应用编程接口，通过解析相对于基底的输入来创建新的 URL 对象。如果基础作为字符串传递，将被解析为等同于*新的 URL(基础)*。

**语法:**

```
new URL(input[, base])
```

可以使用以下方式访问“url”模块:

```
const url = require('url');
```

**参数:**该方法接受两个参数，如上所述，如下所述:

**输入** < *字符串* > **:** 用于解析绝对或相对输入网址的输入是*字符串*类型。如果输入是相对的，则需要基数；如果输入是绝对的，则忽略基数。

**base**<*string*>**|**<*URL*>**:**是 base URL，可以是 *string* 类型，也可以是 *URL* 类型，用于解析输入是否为绝对。

**返回值:**返回新生成的网址以及主机名、协议、路径名等一系列数据。**T3】**

**示例 1:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the 
// new URL() method 

// Using require to access url module 
const url = require('url');

const newUrl = new URL(
    'https://geeksforgeeks.org/p/a/t/h?query=string#hash');

// url array in JSON Format
console.log(newUrl);

const myUR = url.parse(
    'https://geeksforgeeks.org/:3000/p/a/t/h?query=string#hash');
console.log(myUR);
console.log(URL === require('url').URL);

const myURL1 = new URL(
    { toString: () => 'https://geeksforgeeks.org/' });

console.log(myURL1.href)
```

**输出:**

> URL {
> href:' https://geesforgeeks . org/p/a/t/h？query = string # hash '，
> origin:' https://geesforgeeks . org '，
> protocol: 'https:，
> username:“，
> 密码:“，
> host:' geesforgeeks . org '，
> hostname:' geesforgeeks . org '，
> port:“，
> pathname:/p/a/t/h '，【query=string '，
> search params:urlssearcparams { ' query ' =>' string ' }，
> hash:' # hash '
> }
> Url {
> 协议:' ' https:'，
> 斜杠:true，
> auth: null，
> host:' geesforgeeks . org '，
> port: null，
> hostname:' geesforgeeks . org '，
> hash:#query=string '，
> query: 'query=string '，
> 路径名:'/:3000/p/a/t/h '，
> 路径:'/:3000/p/a/t/h？query=string '，
> href:'https://geeksforgeeks.org/:3000/p/a/t/h？query = string # hash '
> }
> true
> https://geeksforgeeks.org/

**示例 2:** **文件名:index.js**

## java 描述语言

```
// Node.js program to demonstrate the 
// new URL() method 

// Using require to access url module 
const url = require('url');
const parseURL = url.parse(
'https://geeksforgeeks.org:3000/p/a/t/h?query=string#hash');

console.log("1 =>", parseURL)

// Prints parsed URL
const newUrl1 = new URL('https://gfg.com');

// prints https://xn--g6w251d/
console.log("2 =>", newUrl1.href)

const myURL = new URL('/alfa',
    'https://akash.org/');
console.log("3 =>", myURL.href)

// https://akash.org/alfa
let newUrl3 = new URL('http://Gfg.com/',
    'https://gfg.org/');

// Prints http://gfg.com/
console.log("4 =>", newUrl3.href)

newUrl4 = new URL('https://Gfg.com/',
    'https://gfg.org/');

// Prints https://gfg.com/
console.log("5 =>", newUrl4.href)

newUrl5 = new URL('foo://Geekyworld.com/',
    'https://geekyworld.org/');
// prints foo://Geekyworld.com/
console.log("6 =>", newUrl5.href)

newUrl6 = new URL('http:Akash.com/',
    'https://akash.org/');
// prints http://akash.com/
console.log("7 =>", newUrl6.href)

newUrl10 = new URL('http:Chota.com/',
    'https://bong.org/');
// prints http://bong.com/
console.log("8 =>", newUrl10.href)

newUrl7 = new URL('https:Chota.com/',
    'https://bong.org/');
// prints https://bong.org/Chota.com/
console.log("9 =>", newUrl7.href)

newUrl8 = new URL('foo:ALfa.com/',
    'https://alfa.org/');

// Prints foo:ALfa.com/
console.log("10 =>", newUrl8.href)
```

使用以下命令运行 **index.js** 文件:

```
node index.js
```

**输出:**

> 1 => Url {
> 协议:' ' https:'，
> 斜杠:true，
> auth: null，
> 主机:' geeksforgeeks.org:3000 '，
> 端口:' 3000 '，
> 主机名:' geeksforgeeks.org '，
> 哈希:' #hash '，
> 搜索:'？query=string '，
> query: 'query=string '，
> 路径名:'/p/a/t/h '，
> 路径:'/p/a/t/h？query=string '，
> href:'https://geeksforgeeks.org:3000/p/a/t/h？query = string # hash '
> }
> 2 =>https://gfg.com/
> 3 =>https://akash.org/alfa
> 4 =>http://gfg.com/
> 5 =>https://gfg.com/
> 6 =>foo://geekyworld . com/
> 7 =>http://akash.com/
> 8 =>http://chota.com/
> 9 =>https://bong.org/Chota.com/
> 10 =>foo:alfa . com/

**参考:**[https://nodejs . org/API/URL . html # URL _ new _ URL _ input _ base](https://nodejs.org/api/url.html#url_new_url_input_base)