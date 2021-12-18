# 为什么快递‘app’和‘服务器’文件分开保存？

> 原文:[https://www . geesforgeks . org/why-express-app-和-server-文件-分开保存/](https://www.geeksforgeeks.org/why-express-app-and-server-files-kept-separately/)

Express 是 Node.js 中用于 web 应用程序的一个简单而简约的框架。Express 为 web 和移动应用程序的开发提供了丰富的功能集合。在任何 web 或移动应用程序中，每个模块或层应该只负责一个任务，而不应该处理其他任务。这允许将应用程序分成更小的构建块，这有助于降低代码复杂性和从其他层提取数据。

将类似的概念应用到 Express 的项目结构中，应用程序逻辑与服务器的分离允许代码模块化并遵循 MVC(模型-视图-控制器)模型。分离对于**减少耦合**和**封装和抽象应用**的内部逻辑至关重要。

下面讨论了 Express 中的每个组件及其职责:

**服务器:**服务器单独负责中间件的初始化，设置引擎，以及请求通过的路由。这些路由由主要应用程序或功能逻辑组成。
下面是进入 server.js 文件的代码片段。

```
// A function to initialize the server
// configuration, middleware and routes
const server = express();

create = function (config) {

    // Get routes from routes directory
    let routes = require('./routes');

    // Configure the server settings
    server.set('env', config.env);
    server.set('port', config.port);
    server.set('hostname', config.hostname);

    // Returns middleware that parses json
    server.use(bodyParser.json());

    // Set up routes for the server
    routes.init(server);
};
```

**App:**‘App’文件包含 web 应用的主要业务逻辑，并负责其执行。它还包含对后端数据库和数据模型的访问。“应用程序”由两个主要组件组成——路由和控制器。这些将在下面讨论。

*   **路线:**路线，顾名思义，负责在应用程序中定义路线。在`routes/index.js`中定义路线的代码片段。

    ```
    // routes/index.js
    server.get('/', function (req, res) {

        // Redirect request to /home route 
        res.redirect('/home');
    });

    server.use('/home', apiRoute);
    server.use('/contact_us', homeRoute);
    server.use('/about', errorRoute);
    ```

*   **控制器:**控制器包含要执行的逻辑。它们还控制渲染的视图。定义控制器的代码片段。

    ```
    // controllers/home.js
    function index (req, res) {
        console.log("On the home page");

        // Write any other application logic here...
    }
    ```

**服务器和 app 分离的优势:**

*   **数据抽象和封装:**虽然服务器只由处理服务器配置、设置中间件和初始化路由的逻辑组成，但应用程序负责应用程序逻辑，并从服务器层抽象出数据模型和业务逻辑。这确保了数据库/数据从服务器层抽象出来，并由应用层封装。
*   **模块化:**通过将服务器和应用功能分开，代码被分成多个模块，每个模块都有一个任务或职责要执行。只要需要，这些模块可以单独使用，因为模块之间的依赖性降低了。通过清晰的逻辑分离可以避免重复代码。
*   **可扩展性:**每个单独的组件都被分配了唯一的职责。这允许快速进行更改，而不必在代码中的任何地方进行更改。例如，考虑一个将要改变的模块的逻辑，它正被用作其他几个功能的子模块。如果逻辑是一个独立的模块，那么只需要在该模块中进行更改，而不是使用逻辑的所有功能。
*   **可重用性:**由于应用程序被划分为多个模块，这些模块被分配了一个任务，因此只要需要，它们就可以在应用程序中多次重用。例如，一个需要多次将分钟转换为秒的应用程序可能会将这种转换定义为一个单独的函数，以避免在整个应用程序中反复重写逻辑的麻烦。