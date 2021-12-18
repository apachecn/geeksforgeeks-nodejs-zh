# node . js 中的–save 和–save-dev 有什么区别？

> 原文:[https://www . geesforgeks . org/node-js/](https://www.geeksforgeeks.org/what-is-the-difference-between-save-and-save-dev-in-node-js/)保存和保存-开发的区别是什么

NPM (Node Project Manager)是一个由 JavaScript 运行时环境 Node.js 使用的包管理器，它有两个非常常用的命令来下载不同的依赖项，`npm install --save [package-name]`和`npm install --save-dev [package-name]`。这两个命令都将导致从 NPM 服务器下载和安装软件包，但它们有一点不同的方式。

**NPM install[package-name]–save**:当–save 在没有-dev 的情况下使用时，表示包是核心依赖。核心依赖是应用程序无法执行其预期工作的任何包。在 package.json 文件的依赖项部分包含核心依赖项的列表。npm 安装也将导致类似的结果。当有人安装你的包时，他们也会安装在 package.json 的 dependencies 部分列出的所有包。

**npm install[package-name]–save-dev**:当–save-dev 与 NPM install 一起使用时，表示该包是开发依赖项。开发依赖是不影响应用程序工作的任何包。在 package.json 文件的 devDependencies 部分包含所有开发依赖项的列表。当有人安装你的包时，他们不会安装任何开发依赖项，但是如果他们克隆了存储库，那么他们也会安装所有的开发依赖项。示例:nodemon

| –保存 | –save-dev |
| --- | --- |
| The installed package is the core dependency. | The installed package is not a core, but a development dependency. |
| All core dependencies are listed under dependencies in package.json | All development dependencies are listed under devDependencies in package.json |
| If a third person tries to install or clone your package, it will be installed. | If a third person tries to clone your package, it will be installed. |
| Examples: express, body-parser, etc. | Example: Node mon |