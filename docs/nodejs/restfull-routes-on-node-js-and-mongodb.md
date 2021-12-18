# 在 Node.js 和 MongoDB 上恢复路由

> 原文:[https://www . geesforgeks . org/restfull-routes-on-node-js-and-MongoDB/](https://www.geeksforgeeks.org/restfull-routes-on-node-js-and-mongodb/)

**REST** 代表表征状态转移，它基本上提供了一种将 HTTP 动词(如 GET、POST、PUT、DELETE)与 CRUD 动作(如 CREATE、READ、UPDATE、DELETE)进行映射的方式。每当我们点击网页上的链接时，我们基本上是在从一个页面向另一个页面进行状态转移。例如，当我们点击博客网站的主页时，我们希望获得存储在服务器数据库中的所有博客，这基本上是 HTTP GET 请求与数据库的 READ 请求的映射。

类似地，还有更多我们与数据库交互的 HTTP 请求，比如创建博客、编辑博客、删除博客等等。RESTfull 路由是如何实现这些映射的标准约定。没有 RESTfull 路线，您就没有必要实现这样的功能，但是这些是大多数开发人员遵循的最简单和标准的路线。我们将通过创建一个简单的博客应用程序来了解它们是如何工作的，在这个应用程序中，我们可以删除、添加、创建、编辑和显示博客。

| 功能 | 小路 | 超文本传送协议 | 预期产出 |
| 索引 | /博客 | 得到 | 列出所有博客文章 |
| 新的 | /博客/新 | 得到 | 显示获取博客信息的表单 |
| 创造 | /博客 | 邮政 | 将博客添加到数据库并重定向到主页 |
| 显示 | /blogs/:id | 得到 | 显示具有给定 id 的博客 |
| 编辑 | /blogs/:id/edit | 得到 | 显示博客的编辑表单 |
| 更新 | /blogs/:id | 放 | 更新特定的博客并重定向到更新的博客 |
| 破坏 | /blogs/:id | 删除 | 删除特定的博客并重定向到主页 |

我们将使用 node.js 来服务网页，使用 MongoDB 来存储数据。整个代码可在 [Github](https://github.com/abhijeetsp98/RESTfull-route) 获得，包括如何与数据库交互和配置所有依赖关系。下面是我们博客文章的**模式**，只是对数据模式略知一二。

**注:**完整代码可在[捷信](https://github.com/abhijeetsp98/RESTfull-route)获得

```js
var blogSchema = new mongoose.Schema({
    title: String,
    image: String,
    body: String,
    created: {type: Date, default: Date.now}
});

var Blog = mongoose.model("Blog", blogSchema);
```

**索引页(GET):** 对于索引页，我们希望显示数据库中存储的所有博客。为此，我们将首先使用 MongoDB 的 find()函数从数据库中获取所有数据，然后将结果发送到显示这些帖子的页面。我们正在查找存储在数据库中的所有博客文章，我们正在使用内部函数检索和处理这些文章，如果出现错误，我们将发送到控制台 error！消息，如果一切正常，那么我们将呈现索引页面，在该页面中，我们将所有博客作为数据(博客)传递，这些数据基本上包含所有博客信息。索引页进一步使用它来显示这些数据。

```js
// Routes
app.get("/blogs", function(req, res){
    Blog.find({}, function(err, blogs){
        if (err) {
            console.log("ERROR!");
        } else {
            res.render("index.ejs", {blogs: blogs});
        }
    });
});
```

**档案名称:index.ejs**

```js
<% blogs.forEach(function(blog){ %>
    <img src="<%= blog.image %>">
    <a href="/blogs/<%= blog._id %>"><%= blog.title %></a>
    <%= blog.created.toDateString() %>...</span>
    <%- blog.body.substring(0, 50) %>
    <a href="/blogs/<%= blog._id %>">Read More</a>   
<% }) %>
```

**新建博客(GET)和创建博客(POST):** 我们想要添加一个新的博客，因此我们需要获取将接受用户输入的表单。因此，首先我们将使用 new.ejs 来呈现表单，然后我们将填充所有信息，之后，我们希望将它保存到数据库中，我们将通过执行 POST 请求来完成。请注意，我们有与上面相同的路由，但这里只更改了请求类型，这将单独处理。我们正在使用 MongoDB create()函数创建一个新的博客文章。如果我们没有得到任何错误，我们将指向主页，在那里用户可以看到博客已经被添加，并确认操作成功执行。

```js
// Render the new.ejs page that contains
// the form for adding a blog
app.get("/blogs/new", function (req, res) {
    res.render("new.ejs");
});

// Add data to database and redirect to
// home page where we see the new page
// with updation
app.post("/blogs", function (req, res) {
    Blog.create(req.body.blog, function (err, newBlog) {
        if (err) {
            console.log("ERROR!");
        } else {
            res.redirect("/blogs");
        }
    });
});
```

**档案名称:new.ejs**

```js
<form action="/blogs" method="POST">
    <label>Title</label>
    <input type="text" name="blog[title]"
                placeholder="Title">
    <label>Image</label>
    <input type="text" name="blog[image]" 
                placeholder="Image">
    <label>Blog Content</label>
    <textarea name="blog[body]"></textarea>
    <input type="submit">
</form>
```

**Show(GET):** 一般来说，博客主页不会完全显示所有的博客，它只显示开始的几行，如果用户想根据标题和预览来阅读，我们希望指向一个新的页面，在这里显示整个博客，在我们的例子中，我们将重定向到 show.ejs HTML 文件。为此，所有的博客都有与之相关联的唯一 id，如果我们想要显示一个特定的博客，我们将简单地获取该博客的 id，并使用 findById()来获取数据并将其发送到 show.ejs HTML 文件，在该文件中将显示数据。

```js
// Routes
app.get("/blogs/:id", function(req, res){
    Blog.findById(req.params.id, 
        function(err, foundBlog){
        if (err) {
            console.log("ERROR!");
        } else {
            res.render("show.ejs", 
                {blog: foundBlog});
        }
    });
});
```

**档案名称:show.ejs**

```js
<%= blog.title %>
<img c src=" <%= blog.image %>">
<span><%= blog.created.toDateString() %></span>
<p><%- blog.body %></p>
<a href="/blogs/<%= blog._id %>/edit">Edit</a>
<form action="/blogs/<%= blog._id %>?_method=DELETE"
            method="POST">
    <button class="ui red inverted button">
        Delete
    </button>
</form>
```

**Edit(GET)和 UPDATE(PUT):** 有时我们想要编辑一个博客，我们首先需要一个唯一的博客 id，在此之后，我们将用户发送到一个不同的页面，在那里显示一个表单，该表单预先填充了以前的数据，用户将在该用户发送到更新的博客之后更新其数据。要做到这一点，首先获得一个请求，然后我们将使用 PUT 请求，该请求将使用 MongoDB 的 findByIdAndUpdate()函数，用给定 id 下已经在数据库中的数据更新数据。

```js
app.get("/blogs/:id/edit", function(req, res){
    Blog.findById(req.params.id, function(err, foundBlog){
        if (err){
            console.log("ERROR!");
        } else {
            res.render("edit.ejs", {blog: foundBlog});
        }
    });
});

app.put("/blogs/:id", function(req, res){
   Blog.findByIdAndUpdate(req.params.id, 
    req.body.blog, function(err,updatedBlog){
       if (err) {
           console.log("ERROR!");
       } else {
           res.redirect("/blogs/"+req.params.id);
       }
   });
});
```

```js
Edit <%= blog.title %>
<form action=
    "/blogs/<%= blog._id %>?_method=PUT"
    method="POST">
    <label>Title</label>
    <input type="text" name="blog[title]" 
            value="<%= blog.title %>">
    <label>Image</label>
    <input type="text" name="blog[image]" 
            value="<%= blog.image%>">
    <label>Blog Content</label>

    <textarea name="blog[body]">
        <%= blog.body%>
    </textarea>
    <input type="submit">
</form>
```

**Destroy(DELETE):** 最后，如果我们想要删除某个特定的博客，我们将简单地使用该博客的 ID，并使用 MongoDB 的 findByIdAndRemove()函数从数据库中删除某个特定的博客。

```js
app.delete("/blogs/:id", function(req, res){
    Blog.findByIdAndRemove(req.params.id, function(err){
        if (err) {
            res.redirect("/blogs");
        } else {
            res.redirect("/blogs");
        }
    });
});
```