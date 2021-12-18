# 如何运行 Node.js 的多个版本？

> 原文:[https://www . geesforgeks . org/如何运行多个版本的节点-js/](https://www.geeksforgeeks.org/how-to-run-multiple-versions-of-node-js/)

通常，我们为我们的 Node.js 项目处理不同的版本，并且很难管理它们，但是幸运的是，有一个叫做 NVM(节点版本管理器)的工具可以帮助管理您的节点版本，并根据您的项目在它们之间切换。

**安装 NVM 模块:**

您可以使用以下命令安装 nvm 模块:

> 使用 curl:
> $ curl-o-https://raw.githubusercontent.com/nvm-sh/v0.34.0/install.sh | bash

安装后，你需要在你的**中增加一点配置。bashrc** 文件如下所示:

```
$ nano ~/.bashrc
```

然后在文件末尾添加以下代码:

```
export NVM_DIR="${XDG_CONFIG_HOME/:-$HOME/.}nvm"
[ -s :$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
```

使用以下命令重新加载 bash:

```
$ source ~/.bashrc 
```

**模块安装:**要安装节点的*最新版本*，可以使用以下命令:

```
$ nvm install node
```

要安装节点的*特定版本*，可以使用以下命令:

```
$ nvm install {node_version}
$ nvm install 10.10.0
```

**列出所有节点版本:**要列出所有安装的版本，可以使用以下命令:

```
$ nvm ls
```

**切换节点版本:**不同节点版本之间的切换可以使用以下命令完成:

```
$ nvm use node  # to use latest version
$ nvm use 10.0.0  # for a specific version
```

**删除节点版本:**可以使用以下命令卸载节点版本:

```
$ nvm uninstall 10.0.0
```

**结论:**如果您正在处理多个需要不同版本节点的项目，管理节点版本非常有用。上面给出了一些重要的命令。

**参考:**

关于 NVM:[https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)

关于 linux 命令行:[https://btholt . github . io/complete-介绍 Linux 和 cli/](https://btholt.github.io/complete-intro-to-linux-and-the-cli/)