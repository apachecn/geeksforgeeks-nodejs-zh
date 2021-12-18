# Node.js Redis 模块

> 哎哎哎:# t0]https://www . geeksforgeeks . org/node-js-redis 模块/

Redis 是一个用于存储数据结构的开源存储。它有多种用途。它用作数据库、缓存和消息代理。它可以存储数据结构，如字符串、散列、集合、排序集合、位图、索引和流。

Redis 对于 Node.js 开发人员非常有用，因为它减少了缓存大小，从而使应用程序更加高效。但是，将 Redis 与 Node.js 应用程序集成起来是非常容易的。

**先决条件:**在开始使用我们的应用程序之前，请确保在您的系统中安装以下内容:

1.  IDE of your choice.
2.  Redis is installed in your system. Use the following command to check the version you are using:

    ```js
    redis cli --version
    ```

3.  Node.js, NPM has been installed and configured in your system.
4.  Basic knowledge of node. js and Redis.

**入门:**首先用 **package.json** 文件初始化应用。键入以下命令:

```js
npm init
```

现在，通过以下命令安装 **redis** 模块:

```js
npm install redis --save
```

现在，创建一个新文件，并将其命名为 **app.js.** 您可以随意命名您的文件。在 **app.js** 文件中，编写以下代码:

**文件名:app.js**

```js
var redis = require("redis");
var client = redis.createClient();

client.on("connect", function() {
  console.log("Connection Successful!!");
});
```

这里，我们导入 **redis** 模块，然后为 redis 创建一个客户端。然后使用客户端来操作模块。在上面的代码中，我们正在创建一个服务器。要运行应用程序，只需键入以下命令:

```js
node app.js
```

上述代码的输出将作为:

```js
Connection Successful!!
```

记录在控制台中

**存储字符串:**要在 Redis 中存储字符串，请在 app.js 文件中编写以下代码:

```js
var redis = require("redis");
var client = redis.createClient();

client.on("connect", function() {
  console.log("Connection Successful!!");
});

client.set("Intern", "gfg", (err, stu) => {
    if (err) console.log(err);
    else console.log(stu);
});
```

**client.set()** 函数采用键值格式。这里**实习生**是关键， **gfg** 是价值。此外，它采用回调函数，如果字符串存储成功，该函数将返回错误(如果有)或记录该值为**确定**。上述代码的输出将是:

```js
Connection Successful!!
OK
```

要获取存储在 redis 数据库中的密钥值，我们将使用**获取**功能，如下所示:

```js
var redis = require("redis");
var client = redis.createClient();

client.on("connect", function() {
  console.log("Connection Successful!!");
});

client.set("Intern", "gfg", (err, stu) => {
    if (err) console.log(err);
    else console.log(stu);
});

client.get('Intern', (err, stu) => {
    if (err) console.log(err);
    else console.log(stu); 
});
```

在这里， **client.get()** 方法会获取**实习生**这个键的值并登录到控制台。上述代码的输出将是:

```js
Connection Successful!!
OK
gfg

```

**存储对象:**要在 **redis 数据库中存储对象，**编写以下代码:

```js
var redis = require("redis");
var client = redis.createClient();

client.on("connect", function() {
  console.log("Connection Successful!!");
});

client.set("Intern", "gfg", (err, stu) => {
    if (err) console.log(err);
    else console.log(stu);
});

client.get('Intern', (err, reply) => {
    console.log(reply); 
});

client.hmset("Interns", { pos: "Tech Writer", Org: "GFG" });
```

现在**键**为**实习生**，其**值**为**{ pos:“Tech Writer”，Org:“GFG”}。**

要从 redis 数据库中获取值，请编写以下代码:

```js
var redis = require("redis");
var client = redis.createClient();

client.on("connect", function() {
  console.log("Connection Successful!!");
});

client.set("Intern", "gfg", (err, stu) => {
    if (err) console.log(err);
    else console.log(stu);
});

client.get('Intern', (err, reply) => {
    console.log(reply); 
})

client.hmset("Interns", { pos: "Tech Writer", Org: "GFG" });

client.hgetall("Interns", (err, stu) => {
    if (err) console.log(err);
    else console.log(stu);
  });
```

这里，使用**hgmetal**方法获取密钥的所有值并将其记录在控制台中。上述代码的输出将是:

```js
Connection Successful!!
OK
gfg
{ pos: 'Tech Writer', Org: 'GFG' }

```

**结论:** Redis 可以让 Node.js 应用快速、强大、高效。Redis 可以被称为各种数据结构的数据库存储。