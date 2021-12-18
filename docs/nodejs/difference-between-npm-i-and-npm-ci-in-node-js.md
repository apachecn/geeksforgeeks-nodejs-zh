# node . js 中 npm i 和 npm ci 的区别

> 原文:[https://www . geesforgeks . org/NPM-I-和-npm-ci-in-node-js/](https://www.geeksforgeeks.org/difference-between-npm-i-and-npm-ci-in-node-js/) 的区别

以下差异涵盖了 ***npm i*** 和 ***npm ci*** 命令之间的不同之处及其功能。 [npm](https://www.geeksforgeeks.org/node-js-npm-node-package-manager/) 被称为节点包管理器，用于管理我们的应用程序所需的模块。

**NPM I:**NPM I(或 npm install)用于安装来自 *package.json* 文件的所有依赖项或开发依赖项。

**语法:**

```js
npm install "package-name"
// OR
npm i "package-name"
```

**npm ci:** CI 代表持续集成，npm ci 用于从 package-lock.json 文件安装所有精确的版本依赖项或 devDependencies。

**语法:**

```js
npm ci
```

*****NPM I*****和** ***npm ci*** **的区别是:****

<figure class="table">

| **s . no .** | **NPM I** | **NPM ci** |
| 1。 | It installs a package and all its dependencies. | Typically used to install dependencies. |
| 2。 | 可能写入 package.json 或 package-lock.json。 | 从不写入 package.json 或包装锁。JSON。 |
| 3。 | You can use this command to add individual dependencies. | Individual dependencies cannot be added with this command. |
| 4。 | It is slow to implement. | The execution speed is faster. |
| 5。 | If there is no dependency in package-lock.json, this command will add it. | If any dependencies are missing or there are incompatible versions, npm ci will throw an error. |
| 6。 | If a *node _ module* already exists, this command will not change it. | If a *node _ modules* already exists, it will be automatically removed before npm ci starts to install. |
| 7。 | Global packages can be installed. | Global package cannot be installed. |
| 8。 | ***NPM I package-name*** is used to add or update dependencies to package.json | Can't be used to write to package.json. |
| 9。 | Npm I may correctly go to package-lock.json to lock some dependencies of the version. | It cannot be written to the package-lock.json. 。 |
| 10。 | In the development process, it is used after pulling the changes of the updated dependency list. | Used for deterministic and repeatable construction. |

</figure>