# 登录 Node.js

> 原文:[https://www.geeksforgeeks.org/logging-in-node-js/](https://www.geeksforgeeks.org/logging-in-node-js/)

[Node.js](https://www.geeksforgeeks.org/nodejs-tutorials/) 是一个 JavaScript 运行时，它建立在 Chrome 的 V8 JavaScript 引擎之上，它的运行时环境包含了我们想要执行的用 JavaScript 编写的程序的所有内容。日志记录是理解 Node.js 程序的完整应用程序生命周期的重要部分。从开始调试到添加新功能，日志通过分析数据提供支持，我们可以通过在错误发生时立即检测错误来更容易、更快地解决错误。Node.js 中有常见的日志记录级别:错误、警告、信息、调试。日志记录包括以更持久的方式记录关于应用程序运行时行为的信息。

登录 Node.js 有以下几种方式:

**console.log:** 最初的日志记录方法是 console.log，这是一个写消息登录调试控制台的函数，但是你很难控制它从代码之外的什么地方记录东西。

语法:

```js
console.log(level, message)
```

**Debug 模块:**使用 Debug 的好处是很多包都用它。当你的后端收到一个互联网请求时，你可以打开它来催促关于像 Express 和 Koa 这样的网络中间件发生了什么的额外信息。好的框架将为您提供如何附加日志中间件，但是您可能不会将所有的小字体也发送到那里。

**中间件**中间件就是你要放入请求管道的东西。设置日志中间件的方法:

*   **应用:**

    ## 爪哇描述语言

    ```js
    const app = express()
    const loggingMiddleware = require('my-logging-middleware')
    app.use(loggingMiddleware)
    ```

*   **路由器:**

    ## java 描述语言

    ```js
    const router = express.Router()
    const routeLoggingMiddleware = require('my-route-logging-middleware')
    router.use(routeLoggingMiddleware)
    ```

**Winston Package:** Winston 包括存储选项、不同的日志级别&查询和一个探查器。

## java 描述语言

```js
const app = express()
const winston = require('winston')
const consoleTransport = new winston.transports.Console()
const myWinstonOptions = {
    transports: [consoleTransport]
}
const logger = new winston.createLogger(myWinstonOptions)

function logRequest(req, res, next) {
    logger.info(req.url)
    next()
}
app.use(logRequest)

function logError(err, req, res, next) {
    logger.error(err)
    next()
}
app.use(logError)
```