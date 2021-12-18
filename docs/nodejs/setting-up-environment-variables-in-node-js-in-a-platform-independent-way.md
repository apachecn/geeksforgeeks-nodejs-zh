# 以平台无关的方式在 Node.js 中设置环境变量

> 原文:[https://www . geesforgeks . org/setting-environment-variables-in-node-js-in-a-platform-independent-way/](https://www.geeksforgeeks.org/setting-up-environment-variables-in-node-js-in-a-platform-independent-way/)

环境变量是确保您宝贵的应用编程接口密钥和机密信息以及自适应代码安全的好方法。然而，当在具有不同操作系统的各种机器上工作时，设置环境变量可能有点乏味。在这种情况下，需要一种可移植的和项目特定的方式来使用它们。这里有一种使用 Node.js 中一个著名的 npm 模块来配置它们的方法

**第一步:安装**[**dotenv**](https://www.npmjs.com/package/dotenv)**NPM 包:**打开命令外壳，导航到项目的根文件夹，通过以下命令安装 [dotenv](https://www.npmjs.com/package/dotenv) npm 包:

```
npm install dotenv

```

如果你喜欢纱线，你可以做:

```
yarn add dotenv

```

**第二步:**创建一个名为 ***的文件。env*** 在项目的根文件夹中，该文件夹将存储所有环境变量

**第三步:项目中需要 dotenv 包**

**仅在本地设置上要求 dotenv 包:** 在项目的 starter JS 文件中，一般是 index.js，尽早导入包，使用如下语句:

```
if(process.env.NODE_ENV !== "production") {
    require('dotenv').config();
}

```

这里，我们只在 NODE_ENV 未设置为 production 时导入包，默认情况下，该选项从不设置。因此，
评估未定义！==“生产”即 True，所以包含 dotenv。但是，生产服务器有自己设置环境变量的方式，因此不需要在发布的应用程序中使用 dotenv。生产时，将 NODE_ENV 环境变量设置为**生产**，这样 dotenv 就不会被包括在内。例如，Heroku 默认将此变量设置为生产状态，如这里所说的，因此我们不必手动操作，查看您的主机提供商的文档以了解更多详细信息。

**第 4 步:在中设置环境变量。env 文件，并像普通环境变量一样使用它们:**将环境变量的键值对存储在。 ***env*** 文件格式如下(没有任何键或值的引号):

```
KEY = VALUE

```

比如你的。env 文件可能如下所示:

```
DB_KEY = YOUR_ACTUAL_DATABASE_ACCESS_KEY
SECRET_TOKEN = VALUE_OF_YOUR_SECRET_TOKEN
ADMIN_EMAIL = xyz@abc.com

```

在代码文件中，可以通过引用它们各自的键来使用这些值，例如，

```
const my_db_key = process.env.DB_KEY
const adminContactMail = process.env.ADMIN_EMAIL

```

**第五步:确保。git 不跟踪 env 文件(出于安全原因，如果您正在使用 git)** 如果项目有 git 设置，请打开。gitignore 文件(如果没有，创建一个)，添加 ***。env*** 如果不存在。这防止了它被跟踪到公共存储库。如果您不打算在项目中使用 git，可以跳过这一步。你可以分享和使用这个。任何计算机上的 env 文件，而无需花费时间设置环境变量。

**注意:**还有其他几个选项，比如，为设置自定义路径。环境文件等。