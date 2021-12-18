# 创建套接字。使用快速生成器的输入输出服务器

> 原文:[https://www . geesforgeks . org/creating-socket-io-server-use-express-generator/](https://www.geeksforgeeks.org/creating-socket-io-server-using-express-generator/)

**插座。IO** 是服务器和客户端实时通信的库。在套接字中。IO，头只共享一次，它也在 TCP 层的顶部工作。网络套接字是套接字的基础。IO 库。实现套接字更容易。不是由快速生成器构成的快速应用程序中的输入输出。

插座。IO 主要工作在基于事件的通信上。在这里，服务器或客户端发出一个事件，它正被另一个捕获。

**模块安装:**

1.  **安装快速发电机:**

    ```
    npm install -g express-generator
    ```

2.  **创建快速应用程序:**

    ```
    npm express applicaion_name
    ```

    例如，您可以创建“npm 快速套接字测试”

3.  我们还可以在制作 express 应用程序时将视图引擎设置为:

    **设置视图引擎(可选)**

    ```
    npm express socketIOTest --view=jade
    ```

4.  **安装插座 IO:**

    ```
    npm install socket.io --save
    npm install
    ```

**创建套接字服务器的步骤:**

1.  转到 App.js 文件并导入套接字。IO 和 http 模块为:

    ```
    var http=require("http");
    var socketio=require("socket.io");

    ```

2.  创建一个套接字 IO 服务器:

    ```
    var createError = require('http-errors');
    var express = require('express');
    var path = require('path');
    var cookieParser = require('cookie-parser');
    var logger = require('morgan');
    var http = require("http");
    var socketio = require("socket.io");
    var app = express();

    var indexRouter = require('./routes/index');
    var usersRouter = require('./routes/users');

    // Create the http server
    const server = require('http').createServer(app);

    // Create the Socket IO server on 
    // the top of http server
    const io = socketio(server);

    // View engine setup
    app.set('views', path.join(__dirname, 'views'));
    app.set('view engine', 'hbs');

    app.use(logger('dev'));
    app.use(express.json());
    app.use(express.urlencoded({ extended: false }));
    app.use(cookieParser());
    app.use(express.static(path.join(__dirname, 'public')));

    app.use('/', indexRouter);
    app.use('/users', usersRouter);

    // Catch 404 and forward to error handler
    app.use(function (req, res, next) {
        next(createError(404));
    });

    // Error handler
    app.use(function (err, req, res, next) {

        // Set locals, only providing error
        // in development
        res.locals.message = err.message;
        res.locals.error = req.app.get('env') 
                === 'development' ? err : {};

        // render the error page
        res.status(err.status || 500);
        res.render('error');
    });

    module.exports = { app: app, server: server };
    ```

3.  现在转到 BIN 文件夹内的 www 文件，用以下代码替换代码:

    ```
    #!/usr/bin/env node

    // Module dependencies
    var app = require('../app').app;
    var debug = require('debug')('socketiotest:server');
    var http = require('http');

    // Get port from environment and store in Express
    var port = normalizePort(process.env.PORT || '3000');
    app.set('port', port);

    // Create HTTP server
    var server = require("../app").server;

    // Listen on provided port, on all
    // network interfaces.

    server.listen(port);
    server.on('error', onError);
    server.on('listening', onListening);

    // Normalize a port into a number,
    // string, or false.
    function normalizePort(val) {
        var port = parseInt(val, 10);

        if (isNaN(port)) {

            // Named pipe
            return val;
        }

        if (port >= 0) {

            // Port number
            return port;
        }

        return false;
    }

    // Event listener for HTTP server "error" event
    function onError(error) {
        if (error.syscall !== 'listen') {
            throw error;
        }

        var bind = typeof port === 'string'
            ? 'Pipe ' + port
            : 'Port ' + port;

        // Handle specific listen errors with
        // friendly messages
        switch (error.code) {
            case 'EACCES':
                console.error(bind 
                    + ' requires elevated privileges');
                process.exit(1);
                break;
            case 'EADDRINUSE':
                console.error(bind + ' is already in use');
                process.exit(1);
                break;
            default:
                throw error;
        }
    }

    // Event listener for HTTP server "listening" event.
    function onListening() {
        var addr = server.address();
        var bind = typeof addr === 'string'
            ? 'pipe ' + addr
            : 'port ' + addr.port;
        debug('Listening on ' + bind);
    }
    ```

这是链接套接字的方式。与快速服务器的 IO。