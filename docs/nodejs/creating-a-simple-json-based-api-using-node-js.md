# 使用 Node.js 创建一个简单的基于 JSON 的 API

> 原文:[https://www . geesforgeks . org/creating-a-simple-JSON-based-API-use-node-js/](https://www.geeksforgeeks.org/creating-a-simple-json-based-api-using-node-js/)

API(Application Programming Interface，应用程序编程接口)结果通常被应用程序使用，有时用于从其庞大的数据库中提取信息，检查特定数据的状态，有时则依赖第三方 API 来显示与用户相关的附加信息。
这里我们将简单公开一个基于 JSON 的 Chemistry API，可以用任何编程语言显示结果。

**创建应用编程接口的步骤:**

*   **第一步:**根据您的操作系统和系统要求，从[这个链接](https://nodejs.org/en/download/)安装 Node.js。
*   **第 2 步:**初始化一个空白文件夹，您将在其中构建应用编程接口。在该文件夹中，创建一个名为 index.js 的空白 JS 文件
*   **第三步:**打开命令提示符，使用光盘(文件夹路径)转到创建的目录。
*   **第四步:**输入`npm init`并完成步骤，回答提问。

为了构建化学应用编程接口，我们需要创建一个空的 JSON 文件，并粘贴来自链接[化学数据](https://drive.google.com/open?id=14qpjtDGa5hrPfVApTt9DU3CrREJloSyD)的数据。现在我们必须包含一些 NodeJS 库，并为 API 设置端口。

```
var fs = require('fs');

// json file with the data
var data = fs.readFileSync('chemistry.json');

var elements = JSON.parse(data);
const express = require("express");
const app = express();

// To solve the cors issue
const cors=require('cors');

app.listen(process.env.PORT, 
    () => console.log("Server Start at the Port"));

app.use(express.static('public'));
app.use(cors());
```

**设计原料药的终点:**

```
// when get request is made, alldata() is called
app.get('/elements', alldata);

function alldata(request, response) {

    // Returns all information about the elements
    response.send(elements);
}
```

这里，“/elements”是端点，当向 API 发出 *get* 请求时，在/elements 端点，调用 alldata()函数。现在 alldata()函数有两个参数(请求和响应)。使用 response.send()，将响应返回给用户。

```
app.get('/elements/:element/', searchElement);

function searchElement(request, response) {
    var word = request.params.element;
    word = word.charAt(0).toUpperCase()
        + word.slice(1).toLowerCase();

    if(elements[word]) {
        var reply = elements[word];         
    }
    else {
        var reply = {
            status:"Not Found"
        }
    }

    response.send(reply);
}
```

"/:element/"是变量端点，用于任何特定元素的请求，例如[https://chemistrydata.herokuapp.com/elements/Hydrogen](https://chemistrydata.herokuapp.com/elements/Hydrogen)

合并所有三段代码创建`index.js`文件。

**文件名:index.js**

```
var fs = require('fs');

// json file with the data
var data = fs.readFileSync('chemistry.json');

var elements = JSON.parse(data);
const express = require("express");
const app = express();

// To solve the cors issue
const cors=require('cors');

app.listen(process.env.PORT, 
    () => console.log("Server Start at the Port"));

app.use(express.static('public'));
app.use(cors());

// when get request is made, alldata() is called
app.get('/elements', alldata);

function alldata(request, response) {

    // Returns all information about the elements
    response.send(elements);
}

app.get('/elements/:element/', searchElement);

function searchElement(request, response) {
    var word = request.params.element;
    word = word.charAt(0).toUpperCase()
        + word.slice(1).toLowerCase();

    if(elements[word]) {
        var reply = elements[word];         
    }
    else {
        var reply = {
            status:"Not Found"
        }
    }

    response.send(reply);
}
```

现在，你们都可以创建一个简单的基于 JSON 的 API，并在 GitHub 中上传整个代码，并将其托管在 Heroku 上。我们已经包含了 Github 存储库链接和 API 文档，请随意探索这个项目。

**github rest link:**T2】https://github . com/aanisha/chemistrdataapi

**原料药文件:** [链接](https://drive.google.com/open?id=10hFZmmxUmn2gPiG6mlpsI-XWlAMjf035)