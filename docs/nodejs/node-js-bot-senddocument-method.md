# Node.js Bot.sendDocument()方法

> 原文:[https://www . geesforgeks . org/node-js-bot-send document-method/](https://www.geeksforgeeks.org/node-js-bot-senddocument-method/)

Node.js 电报机器人应用编程接口中使用了**机器人发送文档()**方法。这个 Node.js 模块与官方的电报机器人应用编程接口进行交互。此方法用于发送扩展名为的文档。pdf，。docx，。txt 等。
**语法:**

```
TelegramBot.sendDocument(chatId, location)

```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **chatId:**chatId 是聊天的唯一标识符，可以是私人的、群组的、超级群组的或频道的，而 userId 只是用户或机器人的唯一标识符。每个客户的信息都包含聊天标识。
*   **位置:**我们要以字符串格式发送的文档的位置。

**返回类型:**函数的返回类型为空。
**安装模块:**使用以下命令安装模块:

```
npm i telegram-bot-api

```

**获取钥匙的步骤:**

1.  首先，通过电报从机器人父亲那里获得 **GET BOT_TOKEN** 。只需在电报中搜索**机器人父亲**并选择验证过的，如下所示:

![](img/00bf1a9a7f602262faf47af3bb85960f.png)

1.  键入*/启动*，然后点击*/新手*，如下图:

![](img/d520cada69e7776bdd44d98ac2dc7f94.png)

2.  现在输入机器人的名称，并且必须是唯一的。

![](img/cef7ef3daa2782f014c9b59a14b32547.png)

2.  现在只需从机器人父亲那里复制令牌。要删除令牌，只需在 BotFather 中搜索/删除令牌。

**项目结构:**

![](img/1747369f8f7ddd682dad752f9865694d.png)

**文件名:bot.js**

## java 描述语言

```
var token = 'Enter the token';

const TelegramBot = require('node-telegram-bot-api');

const bot = new TelegramBot(token, {polling: true});

// Matches "/echo [whatever]"
bot.onText(/\/echo(.+)/, (msg, match) => {

 // The 'msg' is the received Message from Telegram
 // and 'match' is the result of executing the regexp
 // above on the text content of the message

 const chatId = msg.chat.id;

 // The captured "whatever"
 const resp = match[1];

 // Reply to the Bot
 bot.sendMessage(chatId, "Your Document is")

 // Sending the document
 bot.sendDocument(chatId, "document.pdf");
});
```

使用以下命令运行 bot.js 文件:

```
node bot.js

```

**输出:**

![](img/5c1616239e0f2f483146eee84ae1455b.png)