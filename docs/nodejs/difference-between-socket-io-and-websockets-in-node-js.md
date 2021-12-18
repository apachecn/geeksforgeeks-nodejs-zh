# node . js 中 socket.io 和 Websockets 的区别

> 原文:[https://www . geesforgeks . org/socket-io-and-web sockets-in-node-js/](https://www.geeksforgeeks.org/difference-between-socket-io-and-websockets-in-node-js/)之间的区别

**网络套接字**是一种通信约定，它通过一个 TCP 关联提供客户和工作人员之间的双向通信，网络套接字一直保持打开，因此它们允许持续的信息移动。当客户触发对员工的请求时，它不会在得到反应时关闭关联，而是会持续下去，并相信客户或员工会结束请求。

**Socket.io** 是一个库，支持客户和互联网工作人员之间持续的全双工通信。它利用网络套接字约定给出接口。总的来说，它被分成两个部分，网络套接字和套接字。io 都是事件驱动的库

**客户端:**库在程序内部运行。

**服务器端:**是 Node.js 的库

**网络套接字:**以下是亮点–

*   The network socket facilitates the continuous communication between the customer and the web workers.
*   This practice encourages the transition between workers and customers in an ongoing world.
*   This also enables enterprises around the world to continuously improve web applications and build accessibility.
*   It leaves a lot of room for an HTTP association that provides full-duplex communication.
*   Composition of WebSocket convention.
*   Construction of WebSocket convention.

### 出于什么原因我们需要 WebSocket？

*   它提供了全双工通信，这有助于维持客户和互联网工作者之间建立的联系。
*   它同样满足这些原则，并在无明显休眠的情况下提供精确和有效的流场合。
*   WebSocket 消除了开销，减少了不可预测性。
*   它使连续通信变得简单有效。

**Socket.io:** 以下是亮点–

*   It will lead to simultaneous communication with different attachments and directly handle the association.
*   It handles all stages, staff or gadgets to ensure fair and stable quality and speed.
*   Therefore, if necessary, it redesigns the prerequisite as a network socket.
*   It is a custom continuous vehicle agreement execution based on different agreements.
*   It requires that two libraries be used as working libraries at the client.
*   IO chips take away the basic occasions. There are some fixed occasions where attachments can be used on the work side, such as interfaces, messages, disconnection, Ping and reconnection.
*   There are some customer-based convening occasions, such as association, interface error, interface interruption and reconnection, etc.

### 出于什么原因我们需要 Socket。输入输出:

*   它处理你专业选择的所有缺点，以获得全双工连续通信。
*   此外，它还处理不同的帮助级别和程序的不规则性。
*   它同样为基本的分布式框架提供了额外的组件空间，并且像编程重新连接一样思考。
*   目前，AFAIK 是使用最多的一个，它可以更简单地辅助普通的网络附件。
*   WebSocket 和 Socket.io(信息图)之间的无约束关联

## node.js 中 socket.io 和 websockets 的区别:

以下是 WebSocket 与 Socket.io 之间相关性最高的:

<figure class="table">

| **S 号** | **网页 Socket** | **插座。io** |
| 1。 | Is a convention established through TCP connection. | It's a library that works with WebSocket. |
| 2。 | Give full duplex correspondence on TCP connection. | Provide occasion-based communication between program and staff. |
| 3。 | Proxy and load balancer are not supported in WebSocket. | Association can be established within the line of sight of mediation and load balancer. |
| 4。 | Do not adhere to the broadcast. | It supports broadcasting. |
| 5。 | It has no fallback option. | It is the basis of backup choice. |

</figure>