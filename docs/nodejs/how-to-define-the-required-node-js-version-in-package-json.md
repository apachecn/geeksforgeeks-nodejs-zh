# 如何在 package.json 中定义需要的 Node.js 版本？

> 原文:[https://www . geesforgeks . org/如何定义所需的节点-js-包中版本-json/](https://www.geeksforgeeks.org/how-to-define-the-required-node-js-version-in-package-json/)

要在 package.json 文件中定义所需的 Node.js 版本，我们必须经历几个简单的步骤:

**第一步:**我们的第一步也是最重要的一步应该是选择一个我们将要工作的项目，例如，我将选择一个简单的 JavaScript 项目。在这个项目中，我们将有一个 package.json 文件，如果没有，我们将不得不在同一个目录中创建一个 **package.json** 文件。

**步骤 2:** 在创建我们的 Package.json 文件后，我们将使用**引擎**字段来指定项目运行所需的 Node.js 版本，因此我们将在 Package.json 文件中添加几行，遵循相同的语法来指定项目所需的 Node.js 版本:

**语法:**

> “引擎”:{
> 
> " node ":>或< =version_number "，
> 
> " npm ":>或< =version_number "
> 
> },

**输出:**

![](img/5d18fcc0074cf7e3a4ac00e9aa99abe2.png)

描述正确语法的图像

在上面的输出图像中，我们可以看到，我们已经将所需的节点版本定义为大于或等于 **15.0.0** ，npm 版本定义为小于或等于 **5.0.0** ，因此，当我们尝试使用节点运行任何操作时，它将首先检查所需的版本是否与当前版本匹配，如果不匹配，它将显示错误。

**第三步:**当 node.js 版本不匹配时，为了在命令提示符或终端显示错误，我们需要创建一个*。npmrc* 文件位于 package.json 所在的目录中。

**是什么。npmrc 文件？**

简单来说*。npmrc* 文件可以定义为 NPM 的配置文件，它定义了 NPM 在运行命令时应该如何表现的设置。

现在创建一个*。npmrc* 文件并在其中添加以下代码 **engine-strict=true** ，因此如果节点和 npm 版本不匹配，它将强制显示错误。

![](img/c62123a286c0cca75d50e4e4408b4778.png)

**的实际所需语法。npmrc** 文件

**步骤 4:** 现在，我们的最后一步应该是在 Node.js 和 npm 版本不匹配的情况下测试我们是否得到错误，为了测试它，我将使用一个简单的命令 ***npm 安装*** ，我们得到以下错误。

**输出:**

![](img/caac1ee8cf2dfdb7fa834a8a718b74c5.png)

显示节点和 npm 版本不匹配时出错

**参考:**

如何创建 Package.json 文件:[https://www.geeksforgeeks.org/node-js-package-json/](https://www.geeksforgeeks.org/node-js-package-json/)