# node . js 中 Web 角色和工作者角色的区别

> 原文:[https://www . geesforgeks . org/web 角色和工作人员角色在节点中的区别-js/](https://www.geeksforgeeks.org/difference-between-web-role-and-worker-role-in-node-js/)

**Web 角色:** Web 角色是 Azure 中的云服务角色，它被定制为运行由 IIIS(互联网信息服务)支持的编程语言开发的基于 Web 的应用程序，就像我们有 Node JS 一样。

**工作者角色:**工作者角色是 Azure 中的任何角色，它被定制为与 Web 角色一起在后台服务流程中运行应用程序，以频繁完成服务级别任务。

Web 角色和 Worker 角色都是与在端口 80 上的 Azure 云服务上运行应用程序相关的角色。这两种服务可以在同一个 Azure 实例上以相同的方式进行管理和部署。

**Web 角色与 worker 角色的区别:**两种角色的主要区别在于角色在虚拟机(VMs)上的托管方式，就像 Web 服务器通过 IIS 托管应用程序，而 Worker 角色独立运行应用程序一样。

<figure class="table">

| **Web 角色** | **Worker 角色** |
| The Web role is a cloud service role in Azure. | Any role in Azure that runs applications and performs certain tasks can be a worker role. |
| It is suitable for running network applications based on the programming language supported by IIIS. | Suitable for running application and service level tasks. |
| The Web role automatically deploys and hosts the app through IIS. | Run your app independently without IIS. |
| The main role is to easily create web-based applications. | Used to perform background support processes with Web roles. |
| Install IIS by default. | IIS is not installed by default. |
| For some complex applications, incoming requests from users can be handled by web roles. | For some complex applications, incoming requests are passed to the job role for processing. |

</figure>