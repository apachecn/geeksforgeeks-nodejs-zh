# 如何在 Node.js 中存储部署配置文件？

> 原文:[https://www . geesforgeks . org/how-store-deployment-configuration-file-in-node-js/](https://www.geeksforgeeks.org/how-to-store-deployment-configuration-files-in-node-js/)

配置文件(CONFIG 文件)是各种计算机应用程序使用的文件，由决定成功运行应用程序所需设置的参数组成。一般来说，在编写任何软件应用程序之前都会用到它们。

每个网站都有特定的功能，比如收集用户信息。例如，它是一个在线购物网站，然后存储其用户的支付信息。现在，考虑一个网站上的个人信息网关，它的 URL 存储在配置文件中，但是它根据部署而变化。例如，如果它在开发服务器上，那么 URL 将是**info.gfg.com**，当它在处理生产服务器时，那么 URL 将是**secureinfo.gfg.com**。这种类型的设置很容易配置，如果我们也以支付网关为例，它们可以很容易地管理，但是当应用程序必须处理越来越多的部署时，就很难处理它们。

**问题的解决方案:**配置模块是一个用于解决这个问题的模块，因为它以分层的方式为应用程序部署组织配置。这意味着每个部署都有一个专门分配给它的配置文件，并且以某种最佳顺序访问它们。

按照下面给出的步骤，我们可以克服这个问题:

*   **Step 1:** Install the configuration module by running the following code:

    ```js
    npm i config — save
    ```

*   **Step 2:** The configuration module processes the configuration files in the configuration directory under the root directory. You can change it to another directory by executing the following code:

    ```js
    app.js.
    process.env['NODE_CONFIG_DIR'] = __dirname + '/configDir/';

    ```

*   **步骤 3:** 配置文件按照以下顺序加载:

    ```js
    default.json
    {deployment}.json
    local.json
    local-{deployment}.EXT

    ```

    模块从 NODE_ENV 环境变量中选择部署。如果 NODE_ENV 的值是 development，那么将使用 development.json。同样的情况也适用于其他文件。

*   **Step 4:** We have two configuration files, one for local development and the other for production.

    ```js
    local.json
    {
     'dbUrl': 'mongodb://localhost:27017/mydb'
    }
    production.json
    {
     'dbUrl': 'mongodb://some-db-location/dbname'
    }
    var config = require(‘config’);
    config.get(‘dbUrl’);

    ```

通过编写额外的代码`[(var config = require('config'); config.get('dbUrl');]`我们可以解决我们的问题。上一步提到的条件也适用于此，如果开发发生在本地环境中，那么 dbUrl 的值将取自 local.json，当它在生产环境中时(NODE_ENV = production)，那么该值将自动取自 production.json，该解决方案解决了根据应用部署需求配置多个文件的问题。