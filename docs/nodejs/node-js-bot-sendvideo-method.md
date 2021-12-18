# node . js bot . senvideo()方法

> 原文:[https://www.geeksforgeeks.org/node-js-bot-sendvideo-method/](https://www.geeksforgeeks.org/node-js-bot-sendvideo-method/)

Node.js 电报机器人应用编程接口中使用了**机器人发送视频()**方法。这个 Node.js 模块与官方的电报机器人应用编程接口进行交互。此方法用于发送不同格式的视频。

**语法:**

```
TelegramBot.sendVideo(chatId, location)

```

**参数:**该方法接受两个参数，如上所述，如下所述:

*   **chatId:**chatId 是聊天的唯一标识符，可以是私人的、群组的、超级群组的或频道的，而 userId 只是用户或机器人的唯一标识符。每个客户的信息都包含聊天标识。
*   **位置:**我们要以字符串格式发送的视频的位置。

**返回类型:**函数的返回类型为空。

**安装模块:**使用以下命令安装模块:

```
npm i telegram-bot-api

```

**获取钥匙的步骤:**

1.  首先，通过电报从机器人父亲那里获得 **GET BOT_TOKEN** 。只需在电报中搜索**机器人父亲**，并选择如下所示的验证过的:
    ![](img/ed770dbbdc9543bb763c19e559c80c5b.png)
2.  键入*/启动*，然后点击*/新机*，如下图:
    ![](img/7e1485bc848ccfa6b63f2d308c75e6b9.png)
3.  现在输入机器人的名称，并且必须是唯一的。
    ![](img/16c5043413f0b50f826f0fbba9ba6b8b.png)
4.  现在只需从机器人父亲那里复制令牌。要删除令牌，只需在 BotFather 中搜索/删除令牌。

**项目结构:**
![](img/ae46355079a641f3008ac1a22f1a50c1.png)

**文件名:bot.js**

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

  // Reply the message
  bot.sendMessage(chatId, "Your Video is");  

  // Sending the video to the Telegram Bot
  bot.sendVideo(chatId, "h.mp3");  
});
```

使用以下命令运行 bot.js 文件:

```
node bot.js

```

**输出:**
![](img/c36b0cc5943d9f876505a44ef4eec907.png)