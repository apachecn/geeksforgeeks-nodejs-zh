# Node.js | package.json

> 原文:[https://www.geeksforgeeks.org/node-js-package-json/](https://www.geeksforgeeks.org/node-js-package-json/)

**package.json** 文件是 Node.js 系统的心脏。它是任何 Node.js 项目的清单文件，包含项目的元数据。包. json 文件是理解、学习和使用 Node.js 必不可少的部分，它是学习 Node.js 开发的第一步

【package.json 文件由什么组成？
**package . JSON**文件中的元数据信息可以分为以下几类:
**1。识别元数据属性:**它基本上由识别模块/项目的属性组成，如项目名称、模块的当前版本、许可证、项目作者、关于项目的描述等。
**2。功能元数据属性:**顾名思义，它由项目/模块的功能值/属性组成，如模块的入口/起点、项目中的依赖关系、正在使用的脚本、Node 项目的存储库链接等。

**创建 package.json 文件:**
A **package.json** 文件可以通过两种方式创建:
**1。使用 npm init :** 运行该命令，系统期望用户填写如上所述所需的重要信息。它为用户提供了可由用户编辑的默认值。
**语法:**

```
npm init

```

**2。直接写入文件:**可以直接将所有需要的信息写入文件，并可以将其包含在 Node 项目中。

**示例:**一个包含所需信息的演示 **package.json** 文件。

```
{
  "name": "GeeksForGeeks",
  "version": "1.0.0",
  "description": "GeeksForGeeks",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start": "node start.js",
  },
  "engines": {
    "node": ">=7.6.0",
    "npm": ">=4.1.2"
  },
  "author": "GeeksForGeeks",
  "license": "ISC",
  "dependencies": {
    "body-parser": "^1.17.1",
    "express": "^4.15.2",
    "express-validator": "^3.1.2",
    "mongoose": "^4.8.7",
    "nodemon": "^1.14.12",
  },
  "devDependencies": {},
  "repository": {
    "type": "git",
    "url": "https://github.com/gfg/gfg.git" //sample git repo url
  },
  "bugs": {
    "url": "https://github.com/gfg/gfg/issues"
  },
  "homepage": "https://github.com/gfg/gfg#readme"
}

```

**说明** :
**名称:**申请/项目名称。
**版本:**应用的版本。版本应该遵循语义版本控制规则。
**描述:**关于应用、应用目的、使用的技术如 React、MongoDB 等的描述。
**主:**这是 app 的入口/起点。它指定应用程序启动时触发的应用程序主文件。可以使用 **npm start** 启动应用程序。
**脚本:**需要包含在应用程序中才能正常运行的脚本。
**发动机:**所用的**节点**和 **npm** 版本。这些版本是在应用程序部署在像 heroku 或 google-cloud 这样的云上时指定的。
**关键词:**它指定了表征应用程序的字符串数组。
**作者:**由姓名、邮箱等作者相关信息组成。
**许可证:**应用程序确认的许可证在这个键值对中提到。
**依赖项:**使用 **npm** 安装的第三方包或模块在此段中指定。
**开发依赖项:**仅在应用程序的开发部分使用的依赖项在此部分中指定。当应用程序处于生产阶段时，这些依赖关系不会展开。
**存储库:**它包含应用程序代码所在的存储库的类型和 url 的相关信息，在这一部分中会提到。
**bug:**应用程序中应该报告 bug 的 url 和电子邮件都在这一段提到了。

**注意:**这里，**【正文解析器】****【快递】****【快递验证器】****【猫鼬】****【nodemon】**是使用**NPM(Node Package Manager)**安装的模块/包。

**参考文献:**
[http://node source . com/blog/the-basis-package-on-in-nodejs-and-NPM/](http://nodesource.com/blog/the-basics-of-package-json-in-node-js-and-npm/)
[https://dzone . com/articles/the-basis-package-on-in-nodejs-and-NPM](https://dzone.com/articles/the-basics-of-packagejson-in-nodejs-and-npm)