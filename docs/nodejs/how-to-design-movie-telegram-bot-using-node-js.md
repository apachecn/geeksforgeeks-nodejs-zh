# 如何使用 Node.js 设计电影电报机器人？

> 原文:[https://www . geesforgeks . org/how-design-movie-telegram-bot-using-node-js/](https://www.geeksforgeeks.org/how-to-design-movie-telegram-bot-using-node-js/)

Telegram bot API 可用于创建一个聊天机器人，通过发送电影或系列的名称作为命令来返回电影、网络系列和 Tv 系列的完整细节。Telegram 提供了一堆执行不同功能的 API 方法。电报机器人可以用来了解电影的全部细节，而不用去其他网站，如 IMDb 网站等。

**先决条件:**

1.  了解 Javascript 和设置节点环境。
2.  节点的最新版本(版本> 10)
3.  npm 的最新版本(版本> 6)

用于检查系统中是否存在节点和 npm 的命令:

```
$ npm --v
6.14.5

$ node --version
v10.15.0

```

**创建机器人并获取 API 令牌:**

*   打开电报应用，搜索@ BotFather。
*   点击开始按钮或发送/开始。
*   然后发送“/newbot”消息来设置名称和用户名。
*   然后，机器人父亲会给你一个应用编程接口令牌。

**获取电影 API 密钥:**

*   去 [OMDB](http://www.omdbapi.com/apikey.aspx) (打开电影数据库)网站。
*   根据限额创建账户。
*   您将收到自己的应用编程接口密钥。

**模块安装:**

**请求:**要安装该模块，请在终端中键入以下命令。

```
$ npm install --save requests
```

**node-Telegram-Bot-API**:node . js 模块与官方 Telegram Bot API 进行交互。

```
$ npm install node-telegram-bot-api

```

**文件名:bot.js**

```
// Requiring module
var reques = require('requests')
var TelegramBot = require('node-telegram-bot-api')
token = "YOUR-TELEGRAM_API-TOKEN"
movieapi = "YOUR-OMDB_API-TOKEN"

// Create a bot that uses 'polling' 
// to fetch new updates
var bot = new TelegramBot(token, { polling: true });

bot.on("polling_error", (err) => console.log(err));

bot.onText(/\/movie (.+)/, function (msg, match) {

    // The 'msg' is the received Message from
    // user and 'match' is the result of 
    // execution above on the text content

    // Getting the name of movie from the 
    // message sent to bot
    var movie = match[1];
    var chatId = msg.chat.id

    reques('http://www.omdbapi.com/?t=' 
        + movie + '&apikey=movieapi',
        function (error, response, body) {
            if (!error && response.statusCode == 200) {
                bot.sendMessage(chatId, 
                    '_Looking for_ ' + movie + '...', 
                    { parse_mode: "Markdown" }).then(msg) {
                    res = JSON.parse(body)

                    bot.sendPhoto(chatId, res.Poster, {
                        caption: 'Result:\nTitle: ' 
                            + res.Title + '\nGenre: ' 
                            + res.Genre + '\nRated: ' 
                            + res.Rated + '  \nReleased: ' 
                            + res.Released
                    })

                    // Sending back response from the 
                    // bot to the user 
                    // Response has many other details, 
                    // which can be used or sent as per 
                    // requirement
                }
            }
        })
})
```

**运行程序的步骤:**使用以下命令运行 **bot.js** 文件:

```
$ node bot.js
```

现在，进入你的机器人，输入**/电影** *电影名称*并查看结果。

**输出:**

![](img/58632d43f888ed4ae359a665702f80db.png) ![](img/948f36af0682039692eb49d8ed5fb578.png)