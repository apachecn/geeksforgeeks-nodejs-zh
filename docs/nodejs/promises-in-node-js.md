# Node.js

中的承诺

> Original: [https://www.geeksforgeeks.org/promises-in-node-js/](https://www.geeksforgeeks.org/promises-in-node-js/)

**简介：**回调函数用于异步事件。

**示例：**

```js
module.exports = (x, callback) => {
    if (x <= 0)
        setTimeout(() => 
            callback(new Error("Square dimensions
            should be greater than zero: s = " + x),
            null), 2000);
    else
        setTimeout(() => 
            callback(null, {
                perimeter: () => (4*(x)),
                area:() => (x*x)
            }), 2000);
}
```

**什么是承诺？**
承诺基本上是节点回调的推进。 在开发应用程序时，您可能会遇到使用大量嵌套回调函数的情况。

```js
dboper.insertDocument(db, { name: "Test", description: "Test"},
    "test", (result) => {
        console.log("Insert Document:\n", result.ops);

        dboper.findDocuments(db, "test", (docs) => {
            console.log("Found Documents:\n", docs);

            dboper.updateDocument(db, { name: "Test" },
                { description: "Updated Test" }, "test",
                (result) => {
                    console.log("Updated Document:\n", result.result);

                    dboper.findDocuments(db, "test", (docs) => {
                        console.log("Found Updated Documents:\n", docs);

                        db.dropCollection("test", (result) => {
                            console.log("Dropped Collection: ", result);

                            client.close();
                        });
                    });
                });
        });
    });
```

这就是回调函数嵌套导致的情况。 现在设想一下，如果您需要执行多个这样的嵌套操作。 这会使您的代码变得杂乱无章，非常复杂。 在 Node.js 世界中，这个问题被称为**“回调地狱”**。 要解决此问题，我们需要在嵌套时删除回调函数。 这就是承诺进入画面的地方。 节点中的承诺意味着将完成或拒绝的操作。 在完成的情况下，信守诺言，否则，信守诺言。 因此，正如这个词所暗示的那样，要么信守诺言，要么食言。 与回调不同，承诺是可以连锁的。

**回调到承诺**
承诺通知请求是已完成还是被拒绝。 回调可以注册到**.Then()**来处理实现和拒绝。 可以链接**.Then()**来处理实现和拒绝，而可以使用**.catch()**来处理错误(如果有的话)。

**示例：**

```js
dboper.insertDocument(db, 
    { name: "Test", description: "Just a test"},
    "test").then((result) => {
        console.log("Insert Document:\n", result.ops);
    });
```

**嵌套承诺：**您经常会遇到需要使用嵌套承诺的情况。 嵌套的承诺以**开始。然后是()**，在每个**中。然后()**我们有一个**返回语句**。 在**RETURN 语句之后，.Then()**以相同的方式紧随其后。

**示例：**

```js
MongoClient.connect(url).then((client) => {

    const db = client.db(database_name);

    database.insertDocument(db, { name: "Test", 
        description: "Chill Out! Its just a test program!"},
        "test")
        .then((result) => {
            return database.findDocuments(db, "test");
        })
        .then((documents) => {
            console.log("Found Documents:\n", documents);

            return database.updateDocument(db, { name: "Test" },
                    { description: "Updated Test" }, "test");
        })
        .then((result) => {
            console.log("Updated Documents Found:\n", result.result);

            return database.findDocuments(db, "test");
        })
        .then((docs) => {
            console.log("The Updated Documents are:\n", docs);

            return db.dropCollection("test");
        })
        .then((result) => {

            return client.close();
        })
        .catch((err) => alert(err));

})
.catch((err) => alert(err));
```

现在与使用回调相比，我们的代码看起来比以前干净多了。 由于.Then()可以链接在一起，因此每个承诺在代码中都很容易识别。 如果出现错误，则执行.catch(Err)。

**创建自定义承诺**
您始终可以使用新构造函数在 Node 中创建自己的自定义承诺。

```js
var aPromise = new Promise(function(resolve, reject) {
    request.get(options, function(err, resp, body) {
        if (err) {
            reject(err);
        } else {
            resolve(JSON.parse(body));
        }
    })
});
```