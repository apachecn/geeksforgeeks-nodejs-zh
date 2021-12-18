# express js 中的车把模板

> 原文:[https://www . geesforgeks . org/handlebar-templating-in-express js/](https://www.geeksforgeeks.org/handlebars-templating-in-expressjs/)

Handlebars.js 是一个模板引擎，类似于 node.js 中的 ejs 模块，但是功能更强大，使用更简单。它确保了最小的模板化，并且是一个无需逻辑的引擎，可以将视图和代码分开。它可以与 express 一起用作 hbs 模块，可通过 npm 获得。HandleBars 可用于从服务器端的数据向客户端呈现网页。

**命令安装 hbs 模块:**

```
npm i hbs
```

要在 express 中使用手柄，我们需要将 HTML 代码存储到源目录的“视图”文件夹中的. hbs 扩展中，因为 hbs 会在“视图”文件夹中查找页面。

我们在 index.js 文件中需要做的第一件事就是需要 hbs 模块

```
var express = require('express')
var hbs = require('hbs')
var app = express()
```

现在，我们需要更改默认的视图引擎。

```
app.set('view engine', 'hbs')
```

如果视图目录不理想，可以通过以下命令更改视图路径:

```
app.set('views', <pathname>)
```

现在让我们在视图目录中创建一个 demo.hbs 文件，包含以下内容:

```
<!DOCTYPE html>
<html>
    <body>
        <p>This is a Demo Page on localhost!</p>
    </body>
</html>
```

现在，我们通过 express 将网页呈现给本地服务器。

```
app.get('/', (req, res)=>{
    res.render('demo')
})

app.listen(3000)
```

现在，打开浏览器，在网址上输入 *<u>localhost:3000</u>* ，在服务器上验证网页。

现在我们将看到如何将页面动态链接到服务器端数据。
在 index.js 中，我们声明了一个演示对象，实际上，该对象可以是请求体和/或数据库查询的结果。

```
var demo = {
    name : 'Rohan',
    age : 26
}

app.get('/', (req, res)=>{
     res.render('dynamic', {demo : demo})
})
```

在这里，我们将演示对象作为演示发送到我们的 hbs 页面。我们可以检索视图文件夹中的 dynamic.hbs 中的信息。

```
<!DOCTYPE html>
<html>
    <body>
        <p>{{demo.name}} is {{demo.age}} years old.</p>
    </body>
</html>
```

**输出:**

```
Rohan is 26 years old
```

给定多个值，我们可以遍历所有这些值，为每个元素执行相同的功能/显示。

举个例子，把下面的代码加到你的`index.js`中，运行服务器，得到响应。

```
var projects = {
    name : 'Rahul', 
    skills : ['Data Mining', 'BlockChain Dev', 'node.js']
}

app.get('/projects', (req, res)=>{
    res.render('projects', {project : project});
})
```

外部视图/项目的位置。hbs 看起来像:

```
<!DOCTYPE html>
<html>
    <body>
        {{projects.name}} has the following skills : <br>
        {{#each projects.skills}}
            {{this}} <br>
        {{/each}}
    </body>
</html>
```

**输出:**

```
Rahul has the following skills : 
Data Mining
BlockChain Dev
node.js

```