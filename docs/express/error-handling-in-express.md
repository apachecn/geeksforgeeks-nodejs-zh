# 快递中的错误处理

> 原文:[https://www.geeksforgeeks.org/error-handling-in-express/](https://www.geeksforgeeks.org/error-handling-in-express/)

Express 中的错误处理是指处理或处理在执行任何同步代码或异步代码时可能出现的错误。

**我们所说的同步或异步代码是什么意思？**
很多时候，一个操作开始执行，但由于某种原因在完成之前会面临一些延迟。这类操作常见的例子有**的 HTTP 请求**的 AJAX 请求**的 setTimeout** 等功能。这些操作开始，然后在响应返回或计时器结束时结束。当计算机等待这些操作完成时，它继续忙于下一行代码。它一直很忙，但这带来了一个很大的挑战——任何依赖于先前异步代码的代码都可能在**异步**代码完成之前运行，这意味着错误。看看下面-

```
var data = makeAsyncRequest();

// Data is undefined
console.log("Data is " + data);
```

我们可以说，当我们同步执行某件事时，我们会等待它完成，然后再继续另一项任务。当我们异步执行某个任务时，我们可以在它完成之前继续执行另一个任务。上述问题通过使用**回调**、**中间件模块**或者通过使用现代**承诺和等待来解决。**

**捕捉快递中的错误**

*   如果具有路由处理程序和中间件的同步代码抛出任何错误，那么无需任何努力和额外的工作，Express 通过捕获和处理错误来解决它，而不需要我们的任何同意。看看下面的代码–

    ```
    app.get('/', function (req, res) {

        // Express catches this on its own
        throw new Error('Died')
     })
    ```

*   如果一个路由处理程序和中间件调用了异步函数，而异步函数又产生了一些错误，那么我们就要显式地将错误传递给下一个()函数，Express 会在那里进行捕捉和处理。下图将帮助您理解

    ```
    app.get('/', function (req, res, next) {
      fs.readFile('/file-is-not-available', 
            function (err, data) {
        if (err) {

          // Passing errors to 
          // Express explicitly
          next(err) 
        } else {
          res.send(data)
        }
      })
    })
    ```

*   返回承诺的路由处理程序和中间件在拒绝或抛出错误时会自动调用下一个(值)。

    ```
    app.get('/user/:id', async function (req, res, next) { 

        // Async keyword tells that it is
        // an asynchronous function
        var user = await getUserById(req.params.id)    
        res.send(user)
    })
    ```

    恭候关键字可以用来指示后面的函数将返回一个承诺,在执行任何其他相关代码之前应该等待这个承诺“等等”只能在异步函数中使用
    如果**获取用户名**抛出错误或拒绝,下一个（下一个)将被调用抛出的错误或拒绝的值。如果未提供拒绝值,将使用快速路由器提供的默认错误对象调用下一步。如果我们将任何内容传递给下一个()函数（除了字符串“路线”)，快递会将当前请求视为错误,并将跳过任何剩余的非错误处理路由和中间件功能

*   如果序列中给定的回调没有提供数据，只有错误，那么代码可以简化为–

    ```
    app.get('/', [
      function (req, res, next) {
        fs.writeFile('/path-cannot-be-accessed',
                'data', next)
      },
      function (req, res) {
        res.send('OK')
      }
    ])
    ```

    在上面的代码中，**下一个**作为回调提供,回调运行时不考虑错误是否出现。如果没有错误,那么第二个处理程序也会运行,否则表达只会捕获并处理错误

    现在,看看下面的例子–

    ```
    app.get('/', function (req, res, next) {
      setTimeout(function () {
        try {
          throw new Error('Died')
        } catch (err) {
          next(err)
        }
      }, 100)
    })
    ```

*   正如我们所知，如果一个路由处理程序和中间件调用了一个异步函数，而这个异步函数又产生了一些错误，那么我们就必须显式地将错误传递给下一个()函数，Express 将在那里捕获并处理它们。但是，在上面的代码中，错误不是同步代码的部分，所以我们不能简单地将其传递给下一个函数。我们需要首先抛出错误，捕捉那些由异步代码生成的错误，然后将其传递给 Express。为此，我们需要用**试试..抓住**块去抓他们。如果不想用试捕，那就简单用**承诺**如下图–

    ```
    app.get('/', function (req, res, next) {
      Promise.resolve().then(function () {
        throw new Error('Died')

      // Errors will be passed to Express
      }).catch(next)
    })
    ```

    由于承诺会自动捕获同步错误和被拒绝的承诺,您可以简单地提供然后作为最终的捕捉处理程序，快递将捕获错误,因为捕捉处理程序将错误作为第一个参数给出

*   **默认错误处理程序:** 默认错误处理程序在我们调用**下一个** 时捕捉到错误，不要用自定义错误处理程序处理。如果我们想发送一个不同的默认响应，我们必须编写自己的错误处理程序。 这个默认的错误处理中间件功能添加在中间件功能栈的末尾。 如果您将错误传递给 next()，并且没有在自定义错误处理程序中处理它，它将由内置的错误处理程序处理，错误将与堆栈跟踪一起写入客户端。生产环境中不包括堆栈跟踪。

    写入错误时,以下信息会自动添加到响应中:

    *   从 err.statusCode(或 err . status code)设置 res.statusCode。如果该值在 4xx 或 5xx 范围之外，它将被设置为 500。
    *   RES . status 消息根据状态代码进行设置。
    *   在生产环境中，正文将是状态代码消息的 HTML，否则将是 err . stack .
    *   err . headers 对象中指定的任何头。

    如果在开始写入响应后调用下一个()时出现错误（例如,如果您在将响应流式传输到客户端时遇到错误)，快递默认错误处理程序将关闭连接并使请求失败

    T80】因此,当您添加自定义错误处理程序时,当标题已经发送到客户端时,您必须委托给默认的快速错误处理程序:

    ```
    function errorHandler (err, req, res, next) {
      if (res.headersSent) {
        return next(err)
      }
      res.status(500)
      res.render('error', { error: err })
    }
    ```

    请注意,如果您在代码中多次调用下一个()并出现错误,则默认错误处理程序可能会被触发,即使定制的错误处理中间件已经就位

    **如何编写错误处理程序？**

    我们声明中间件功能的方式,以同样的方式定义错误处理功能。但是,错误处理函数有四个参数,而不是三个:(错误，请求，停止，下一步).例如–

    ```
    app.use(function (err, req, res, next) {
      console.error(err.stack)
      res.status(500).send('Something broke!')
    })
    ```

    我们需要最后定义错误处理中间件,在其他 app.use()之后,并路由调用。示例如下所示–

    ```
    app.get('/', (req, res, next) => {
     req.foo = true;
      setTimeout(() => {
        try {
          throw new Error('error');
        }
        catch (ex) {
          next(ex);
        }
      })
    });
    app.use((err, req, res, next) => {
      if (req.foo) {
        res.status(500).send('Fail!');
      }
      else {
        next(err);
      }
    })
    app.use((err, req, res, next) => {
      res.status(500).send('Error!')
    })
    ```