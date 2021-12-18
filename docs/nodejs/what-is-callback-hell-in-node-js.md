# node . js 中的回调地狱是什么？

> 原文:[https://www . geeksforgeeks . org/什么是回调地狱节点-js/](https://www.geeksforgeeks.org/what-is-callback-hell-in-node-js/)

要知道什么是回调地狱，我们必须从同步和异步 Javascript 开始。

**什么是同步 Javascript？**
在 Synchronous Javascript 中，当我们运行代码时，结果会在浏览器能做的时候尽快返回。一次只能发生一个操作，因为它是单线程的。因此，当一个操作正在执行时，所有其他进程都被搁置。

**什么是异步 Javascript？**

*   Javascript 中的一些函数需要 AJAX，因为一些函数的响应不是即时的。这需要一些时间，下一个操作不能立即开始。它必须在后台等待函数完成。在这种情况下，回调需要是异步的。
*   有一些允许 AJAX 的外部 Javascript 网络应用程序接口——异步 Javascript 和 XML。
    在 AJAX 中，可以同时执行很多操作。

**什么是回调？**

*   回调只不过是需要一些时间才能产生结果的函数。
*   通常这些异步回调(异步的缩写)用于从数据库访问值、下载图像、读取文件等。
*   由于这些需要时间来完成，我们既不能继续下一行，因为它可能会抛出一个错误说不可用，也不能暂停我们的程序。
*   因此，我们需要存储结果，并在完成时调用。

**什么是回调地狱？**
这是用复杂的嵌套回调进行编码导致的一个大问题。这里，每个回调都带有一个参数，该参数是之前回调的结果。以这种方式，代码结构看起来像一个金字塔，很难阅读和维护。此外，如果一个函数有错误，那么所有其他函数都会受到影响。

**例:**这是典型回调地狱的例子。

```js
app.get("/details", function (req, res) {
    var name = req.query.name;
    console.log(name);

    Scopus.find({ name: name },
        { '_id': 0, 'authorId': 1 },
        function (err, result) {
            if (err) { }
            else {
                var searchResult = result[0]["authorId"];
                console.log(searchResult);
                var options = {
                    url: "https://api.elsevier.com/content/author/author_id/"
                        + searchResult + "?apiKey",
                    headers: { 'Accept': 'application/json' }
                };
                request(options, function (error, response, body) {
                    if (error) {

                        // Print the error if one occurred
                        console.error('error in Authors :', error);

                        // Print the response status code if a response was received
                        console.log('statusCode:', response && response.statusCode);
                        res.send("error")
                    }
                    else if (!error) {
                        var jsonObj = JSON.parse(body);
                        if (jsonObj['author-retrieval-response'] == undefined) {
                            res.send("No details");
                        }
                        else {
                            var reqData = jsonObj['author-retrieval-response'][0];
                            var authprofile = reqData["author-profile"]
                            var names = authprofile["preferred-name"]["indexed-name"]
                            console.log(names);
                            var citation = reqData["coredata"]["citation-count"];
                            var query = { authorId: searchResult };

                            Scopus.findOneAndUpdate(query, {
                                name: names,
                                citationCount: citation
                            }, function (err, doc, res) {
                                if (err) {
                                    console.log("error");
                                }
                                else {
                                    console.log("success");
                                }
                            })
                            res.render("details", { data: reqData });
                        }
                    }
                });
            }
        })
});
```

您可以注意到嵌套回调看起来像一个金字塔，很难理解。

**如何逃离回调地狱？**

*   JavaScript 提供了一种逃离回调地狱的简单方法。这是通过事件队列和承诺来完成的。
*   **promise 是从任何异步函数返回的对象，可以根据前一个函数的结果向其添加回调方法。**
*   承诺有用。然后()方法调用异步回调。我们可以链接任意多的回调，订单也得到严格维护。
*   承诺有用。fetch()方法从网络中获取对象。它还使用。catch()方法在任何块失败时捕获任何异常。
*   所以这些承诺被放在事件队列中，这样它们就不会阻塞后续的 JS 代码。同样，一旦返回结果，事件队列就完成其操作。
*   还有其他有用的关键字和方法，如 async、wait、settimeout()来简化和更好地利用回调。