# 在 Node.js 中处理用户代理

> 原文:[https://www . geesforgeks . org/handling-user-agent-in-node-js/](https://www.geeksforgeeks.org/handling-user-agents-in-node-js/)

用户代理是字符串形式的信息。该字符串允许服务器识别来自网络浏览器的传入请求的应用程序类型、操作系统、版本和供应商。用户代理的通用结构将是-

```
User-Agent: product / product-version comment

```

这里，发送请求的网页浏览器的名称将被写入**产品**。产品版本将写在**产品版本**中，**评论**可选。它包含有关产品的更多信息。例如，如果网络浏览器是火狐，那么用户代理将是-

```
Mozilla/5.0 (system-information) 
    platform (platform-details) extensions
```

用户代理模块提供网络浏览器属性。它还提供了阻止自动浏览器所需的数据。

**用户代理模块设置:**要启用该模块，首先需要用 **package.json** 文件初始化应用程序，然后安装**用户代理**模块。因此，让我们首先用 package.json 文件–
初始化我们的应用程序

```
npm init

```

现在，使用–
安装模块

```
npm install user-agents --save

```

要在应用程序中使用该模块，只需编写以下代码–

```
const userAgent = require('user-agents');

```

**实现:**安装完模块之后，现在我们来看看这个模块的一些实现。这个模块最基本的实现是生成随机用户代理。要生成随机用户代理，请在 main.js 文件–
中编写以下代码

```
const UserAgent = require('user-agents'); 

const userAgent = new UserAgent();
console.log(userAgent.toString());
```

这里，我们正在借助**新的**关键字创建一个用户代理模块的实例。然后，我们在控制台中记录随机生成的用户代理的字符串格式。上述代码的输出将是–

```
Mozilla/5.0 (Windows NT 10.0; Win64; x64) 
AppleWebKit/537.36 (KHTML, like Gecko) 
Chrome/80.0.3987.132 Safari/537.36

```

此外，如果我们想以 JSON 格式打印数据，请编写以下代码–

```
const UserAgent = require('user-agents'); 

const userAgent = new UserAgent();
console.log(JSON.stringify(userAgent.data, null, 1));
```

这里， **stringify()** 函数将把 JavaScript 值转换成 JSON。它需要三个参数，第一个参数是要转换成 JSON 的值，第二个参数是将结果转换的替换函数，第三个参数是用于添加缩进、换行符，以便转换后的 JSON 字符串易于读取。

上述代码的输出将是–

```
{
 "appName": "Netscape",
 "connection": {
  "downlink": 10,
  "effectiveType": "4g",
  "rtt": 100
 },
 "platform": "Win32",
 "pluginsLength": 3,
 "vendor": "Google Inc.",
 "userAgent": 
    "Mozilla/5.0 (Windows NT 6.1; Win64; x64) 
     AppleWebKit/537.36 (KHTML, like Gecko) 
     Chrome/80.0.3987.132 Safari/537.36",
 "viewportHeight": 790,
 "viewportWidth": 1580,
 "deviceCategory": "desktop",
 "screenHeight": 900,
 "screenWidth": 1600,
 "weight": 0.00007295599223907504
}

```

该模块还提供了限制应用程序仅在指定设备中使用的功能。例如–

```
const UserAgent = require('user-agents'); 

const userAgent = new UserAgent({ deviceCategory: 'mobile' })
```

在这里，我们将我们的应用程序限制为仅在移动设备中使用。除了手机，我们还可以写**桌面**或者**平板**。
此外，如果您想要创建具有相同配置或属性的多个用户代理，那么编写以下代码–

```
const UserAgent = require('user-agents');

const userAgent = new UserAgent({ 
    platform: 'Win64', 
    deviceCategory: 'desktop' 
});

const userAgents = Array(50).fill()
        .map(() => userAgent());
```

这里，我们创建了一个用户代理实例，其属性为**平台**和**设备类别**。我们限制其使用 **Windows 64** 平台，只能在**桌面**上运行。然后，我们创建了另外 50 个具有相同配置的用户代理的阵列。
我们还可以对我们的应用程序应用过滤器，返回的用户代理将与应用的过滤器相匹配。因此，要应用过滤器，请编写以下代码–

```
const UserAgent = require('user-agents');

const userAgent = new UserAgent(/Chrome/);
console.log(userAgent.toString());
```

这里，我们通过过滤器为 **/Chrome/** 。返回的用户代理将包含 **Chrome** 子字符串。我们还可以将过滤器和一系列配置组合起来，应用于返回的用户代理。
例如–

```
const UserAgent = require('user-agents');

const userAgent = new UserAgent([
    /Chrome/,
    {
      deviceCategory: 'tablet',
      platform: 'Win64'
    }
]);
```

在这里，我们将过滤器应用为 **Chrome** 以及返回的用户代理上的一系列配置。

**结论:**在本文中，我们了解了 JavaScript 的**用户代理**模块，并研究了如何在 JavaScript 文件中设置该模块。我们还看到了这个模块的一些实现。