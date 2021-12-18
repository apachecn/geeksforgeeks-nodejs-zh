# 如何在 Node.js 中根据查询参数发送不同的 HTML 文件？

> 原文:[https://www . geesforgeks . org/如何发送基于查询的不同 html 文件-节点中的参数-js/](https://www.geeksforgeeks.org/how-to-send-different-html-files-based-on-query-parameters-in-node-js/)

下面的方法介绍了如何根据 Node.js 中的查询参数发送不同的 HTML 文件

**方法:**通过接收查询参数，将不同的 HTML 文件映射到各自的参数，可以轻松完成任务。

**步骤 1:** 创建您的项目文件夹，并使用以下命令安装 **express** 模块:

```js
npm install express
```

**第二步:**在你的项目根目录下创建一个 ***main.js*** 文件，并在里面写下下面的代码。

## main . js

```js
var express = require('express');
var app = express();
const fs = require("fs");

// Helper function to read and serve html files 
// according to the requested paths 
function readAndServe(path, res) {
    fs.readFile(path, function (err, data) {
        res.end(data);
    })
}

// Setting get request path to receive id as query parameter 
app.get('/:id', function (req, res) {
    console.log(req.params);

    // Mapping different id's with respective html files
    if (req.params.id == "id1")
        readAndServe("./id1.html", res);
    else if (req.params.id == "id2")
        readAndServe("./id2.html", res);
    else {
        res.end("Invalid request");
    }
});

app.listen(8080, () => { console.log("Server Listening on Port 8080") });
```