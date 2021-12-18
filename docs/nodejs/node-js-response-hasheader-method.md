# Node.js response.hasHeader()方法

> 原文:[https://www . geesforgeks . org/node-js-response-hasheader-method/](https://www.geeksforgeeks.org/node-js-response-hasheader-method/)

***response . hasheader()***(在 v7.7.0 中添加)属性是“ *http* ”模块的内置属性，如果名称标识的标头当前设置在传出标头中，则返回 *true* 。标题名称匹配不区分大小写。由 *response.getHeaders()* 方法返回的对象通常不是从 JavaScript 对象继承的。

为了得到响应和恰当的结果，我们需要导入“ *http* ”模块。

```js
const http = require('http');
```

**语法:**

```js
response.hasHeader(name);
```

**参数:**该属性接受一个参数，如上所述，如下所述:

*   **名称:**是要检查是否存在的表头值的名称。

**返回值** < *布尔* > **:** 如果当前设置了表头名称，则返回*真*，否则返回*假*。

下面的例子说明了在 Node.js 中 *response.hasHeader()* 属性的使用

**示例 1:** **文件名:index.js**

## java 描述语言

```js
// Node.js program to demonstrate the
// response.hasHeaders() Method

// Importing http module
var http = require('http');

// Setting up PORT
const PORT = process.env.PORT || 3000;

// Creating http Server
var httpServer = http.createServer(
    function (req, response) {

    // Setting up Headers
    response.setHeader('Alfa', 'Beta');

    // response.setHeader('', 'Beta'); // Throws Error
    // response.setHeader(); // Throws Error
    response.setHeader('Alfa1', '');
    response.setHeader('Alfa2', 5);
    response.setHeader('Cookie-Setup',
            ['Alfa=Beta', 'Beta=Romeo']);

    // Checking the headers
    const hasHeardere = response.hasHeader('Cookie-Setup');
    const hasHearder0 = response.hasHeader('Alfa');
    const hasHearder1 = response.hasHeader('Alfa1');
    const hasHearder2 = response.hasHeader('Alfa2');
    const hasHearder3 = response.hasHeader('Content-Type');

    // Printing output
    console.log("When Header is set an Array:", hasHeardere);
    console.log("When Header is set Beta:", hasHearder0);
    console.log("When Header is set '':", hasHearder1);
    console.log("When Header is set number 5:", hasHearder2);
    console.log("When Header is not set:", hasHearder3);

    // Getting the set Headers
    const headers = response.getHeaders();

    // Printing those headers
    console.log(headers);

    var Output = "Hello Geeksforgeeks..., " +
        "When Header is set 'Beta': " + hasHeardere +
        ", When Header is set '':" + hasHearder1 +
        ", When Header is set number 5:" + hasHearder2 +
        ", When Header is not set:" + hasHearder3;

    // Prints Hello Geeksforgeeks...
    // on browser in response
    response.write(Output);
    response.end();
});

// Listening to http Server
httpServer.listen(PORT, () => {
    console.log("Server is running at port 3000...");
});
```

使用以下命令运行 **index.js** 文件:

```js
node index.js
```

**输出:**

> **输出:**在控制台…
> 
> >>服务器在 3000 启动…
> 
> 当标题设置为数组时:真
> 
> 当标题设置为“测试版”时:真
> 
> 当“标题”设置为“真”时
> 
> 当标题设置为 5 时:真
> 
> 未设置标题时:假
> 
> > >[对象:空原型]{ 0
> 
> 阿尔法:贝塔，
> 
> alfa1:“，
> 
> 阿尔法 2: 5，
> 
> cookie-setup”:[' Alfa = Beta '，' Beta =罗密欧']}

**//现在在浏览器中运行 http://localhost:3000/即可。**

> **输出:**在浏览器中…
> 
> Hello Geeksforgeeks…，当 Header 设置为‘Beta’:true，当 Header 设置为:true，当 Header 设置为数字 5:true，
> 
> 未设置标题时:假

**参考:**[https://nodejs . org/API/http . html # http _ response _ hasheader _ name](https://nodejs.org/api/http.html#http_response_hasheader_name)