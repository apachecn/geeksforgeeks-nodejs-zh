# Node.js URL.format API

> 原文:[https://www.geeksforgeeks.org/node-js-url-format-api/](https://www.geeksforgeeks.org/node-js-url-format-api/)

借助`**url.format()**`方法，我们可以根据需要格式化主机名。我们有不同类型的其他参数，可以用来生成主机名或根据需要更改主机名。

> **语法:** `**url.format(URL[, options])**`
> **参数:**
> 
> *   **auth** 为布尔值，如果为真，则必须提供用户名和密码。
> *   **片段**如果为真，则应该包含片段，否则不包含。
> *   **搜索**如果为真，则提供搜索查询，否则不提供。
> *   **unicode** 如果为真，则主机名中出现的 unicode 字符应直接编码，否则不编码。
> 
> **返回:**返回新生成的**网址或主机名**

**示例 1 :** 在本例中，我们首先在节点中导入 **url** 模块。然后为了生成或格式化随机网址，我们使用`**url.format()**`方法。

```js
// node program to demonstrate the  
//  url.format(URL[, options])

//importing the module 'url' 
const url = require('url');

// creating and initializing myURL 
var myURL = new URL(''https://abc:xyz@example.com#geeks'); 

// Display href value of myURL before change 
console.log("Before Change"); 
console.log(myURL.href); 

// using format method
myURL = url.format(myURL, { fragment: true, 
    unicode: true, auth: false });

// Display href value of myURL after change 
console.log("After Change"); 
console.log(myURL.href); 
```

**输出:**

```js
Before Change
'https://abc:xyz@example.com#geeks'

After Change
'https://example.com/#geeks'

```

**例 2:**

```js
// node program to demonstrate the  
//  url.format(URL[, options])

//importing the module 'url' 
const url = require('url');

// creating and initializing myURL 
var myURL = new URL('https://geeksforgeeks'); 

// Display href value of myURL before change 
console.log("Before Change"); 
console.log(myURL.href); 

// using format method
console.log("After Change"); 
console.log(url.format(myURL, { fragment: false,
    unicode: true, auth: false }));
```

**输出:**

```js
Before Change
https://geeksforgeeks

After Change
https://geeksforgeeks

```